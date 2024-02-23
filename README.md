<!-- @format -->

# English README 　[Jump to Japanese Version](#japanese)

# Ethernaut Solutions

- The Ethernaut is a Web3/Solidity-based coding wargame, played in the Ethereum Virtual Machine.
- Each level is a smart contract that needs to be 'hacked'.

Here are the writeups of my solutions levels I cleared.
** I will not recommend you to look at solutions I wrote. Solve it yourself for your learning 😛 **

# How to use Ethernaut

- To use ethernaut, you need to use the console from the developper tool of your browser in the first place.
- If your confortable with Foundry and Methods call using `cast` and `send`, you can also solve problem from Foundry framework.
- If you are not confortable yet with ABI, then it is a great way to learn about it and how to call any contract by external calls.
- In higher difficulty levels, you will need to wrote smart contracts and interfaces to hack some smart contract externally for clearing levels.

## Ethernaut 0. Hello Ethernaut

<br/>
<p align="center">
<img src="https://github.com/Jer-B/Ethernaut_Hello_-spoil-/blob/main/images/hello.png" width="900" alt="Ethernaut Hello">
</p>
<br/>

Introductory level.<br /><br />
Link to the repository: [Here](https://github.com/Jer-B/Ethernaut_Hello_-spoil-).
<br />
<br />
<br />

## Ethernaut 1. Fallback

<br/>
<p align="center">
<img src="https://github.com/Jer-B/Ethernaut_Fallback_-spoil-/blob/main/images/fallback.png" width="900" alt="Ethernaut Fallback">
</p>
<br/>

The goal is to become the Owner of the smart contract to be able to steal all the funds in it.<br /><br />
Link to the repository: [Here](https://github.com/Jer-B/Ethernaut_Fallback_-spoil-).
<br />
<br />
<br />

## Ethernaut 2. Fallout

<br/>
<p align="center">
<img src="https://github.com/Jer-B/Ethernaut_Fallout_-spoil-/blob/main/images/fallout.png" width="900" alt="Ethernaut Fallout">
</p>
<br/>

The goal is to become the Owner of the smart contract.<br />

- The best hint is in the presentation image of the problem. <br /><br />
  Link to the repository: [Here](https://github.com/Jer-B/Ethernaut_Fallout_-spoil-).
  <br />
  <br />
  <br />

## Ethernaut 3. Coinflip

<br/>
<p align="center">
<img src="https://github.com/Jer-B/Ethernaut_Coinflip_-spoil-/blob/main/images/coinflip.png" width="900" alt="Ethernaut coinflip">
</p>
<br/>

The goal is to guess 10 times the right side on which the coin is gonna flip when calling the `flip()` function.<br /><br />
Link to the repository: [Here](https://github.com/Jer-B/Ethernaut_Coinflip_-spoil-).
<br />
<br />
<br />

## Ethernaut 4. Telephone

<br/>
<p align="center">
<img src="https://github.com/Jer-B/Ethernaut_Telephone_-spoil-/blob/main/images/Telephone.png" width="900" alt="Ethernaut Telephone">
</p>
<br/>

The goal is to become the Owner of the smart contract.<br />

- In the `Telephone` smart contract, there is a logic that if transaction made that is not from `tx.origin` we can become the owner.<br />
- It is a problem to show what to use when it comes to the transaction origine. `tx.origin` or `msg.sender` .<br />
- The `tx.origin` global variable refers to the original external account that started the transaction while `msg.sender` is a direct transaction from an user.<br /><br />
  Link to the repository: [Here](https://github.com/Jer-B/Ethernaut_Telephone_-spoil-).
  <br />
  <br />
  <br />

## Ethernaut 5. Token

<br/>
<p align="center">
<img src="https://github.com/Jer-B/Ethernaut_Token_-spoil-/blob/main/images/token.png" width="900" alt="Ethernaut Token">
</p>
<br/>

The goal is to get all ERC20 Tokens of the contract transfered to our balance

- The trick in that contract is that it is done under `Solidity 0.6.0`. under `0.8.0` we need to use a library called `SafeMath` for dealing with numbers.
- Without `SafeMath` all solidity contracts with a compiler version under `0.8.0` have an `underflow` and `overflow` problem.
- Example: We have an integer of type `uint` with value of `20`. Let say we do `20 + 1`, we don't get `21`. Instead we get `1` by going over `21`. Which is the `UintMax` in this case.
- Meaning we can have all tokens of the total supply.
- SafeMath was used to prevent this problem. Since `0.8.0` it is integrated into solidity by default.
  Link to the repository: [Here](https://github.com/Jer-B/Ethernaut_Token_-spoil-).
  <br />
  <br />
  <br />

## Ethernaut 8. Vault

<br/>
<p align="center">
<img src="https://github.com/Jer-B/Ethernaut_Vault_-spoil-/raw/main/images/vault_contract.png" width="700" alt="Ethernaut Vault">
</p>
<br/>

The goal is to unlock the contract by finding the `Bytes32` password.

- The solution here is to find the value of the `private` variable

  Link to the repository: [Here](https://github.com/Jer-B/Ethernaut_Vault_-spoil-).
  <br />
  <br />
  <br />

## Ethernaut 9. King

<br/>
<p align="center">
<img src="https://github.com/Jer-B/Ethernaut_King_-spoil-/raw/main/images/king_contract.png" width="700" alt="Ethernaut King">
</p>
<br/>

The goal is to take control of the contract.

- The solution here is to send an amount of ether superior to the prize to the contract. Here is an easy explanation:
- To do so we can only use the `call` function.
- `transfer` and `send` can not be used as when calling the `receive` function of the contract, it will revert the transaction due to the gas cap of 2300.
- `call` function does not have this gas cap and can be used to send ether to the contract.
  Link to the repository: [Here](https://github.com/Jer-B/Ethernaut_King_-spoil-).
  <br />
  <br />
  <br />

## Ethernaut 10. Re-Entrancy

<br/>
<p align="center">
<img src="https://github.com/Jer-B/Ethernaut_ReEntrancy_-spoil-/raw/main/images/reentrant_contract.png" width="700" alt="Ethernaut King">
</p>
<br/>

The goal is to empty the contract of its funds.

- What is going to happen, we need to call `donate` to set a `value` to the balance of contract used for the attack.
- Then call `withdraw` to empty the contract. Since the state changes happen later on, the `receive` function will be called and the attack will be repeated until the attacked contract balance is less than `0.001eth`.
  Link to the repository: [Here](https://github.com/Jer-B/Ethernaut_ReEntrancy_-spoil-).
  <br />
  <br />
  <br />

<a name="japanese"></a>

# 日本語版の README

# Ethernaut の解決策

- Ethernaut は、Web3/Solidity ベースのコーディングウォーゲームで、Ethereum Virtual Machine (EVM) でプレイされます。
- 各レベルはハッキングする必要があるスマートコントラクトです。

これはクリアしたレベルの解決策です。
**解決策を見ることをお勧めしません。学習のために自分で解決してください 😛 **

# Ethernaut の使用方法

- Ethernaut を使用するには、まずブラウザの開発者ツールからコンソールを使用する必要があります。
- Foundry と cast および send を使用した方法の呼び出しに慣れている場合、Foundry フレームワークから問題を解決することもできます。
- まだ ABI に慣れていない場合、それを使用して任意のコントラクトを外部呼び出しで呼び出す方法について学び、理解するのに最適な方法です。
- より高難度のレベルでは、スマートコントラクトとインターフェースを作成して、いくつかのスマートコントラクトを外部からハッキングするために解レベルをクリアする必要があります。

## Ethernaut 0. Hello Ethernaut

<br/>
<p align="center">
<img src="https://github.com/Jer-B/Ethernaut_Hello_-spoil-/blob/main/images/hello.png" width="900" alt="Ethernaut Hello">
</p>
<br/>

これは導入的なレベルである。<br /><br />

レポジトリーへのリンクは: [こちら](https://github.com/Jer-B/Ethernaut_Hello_-spoil-)。
<br />
<br />
<br />

## Ethernaut 0. Fallback

<br/>
<p align="center">
<img src="https://github.com/Jer-B/Ethernaut_Fallback_-spoil-/blob/main/images/fallback.png" width="900" alt="Ethernaut Hello">
</p>
<br/>

目標は、そのスマートコントラクトのオーナーになり、中にあるすべての資金を奪うことです。<br /><br />

レポジトリーへのリンクは: [こちら](https://github.com/Jer-B/Ethernaut_Fallback_-spoil-)。
<br />
<br />
<br />

## Ethernaut 2. Fallout

<br/>
<p align="center">
<img src="https://github.com/Jer-B/Ethernaut_Fallout_-spoil-/blob/main/images/fallout.png" width="900" alt="Ethernaut Fallback">
</p>
<br/>

- 目標は、スマートコントラクトの所有者になることです。<br />
  最も役立つヒントは、問題のプレゼンテーション画像にあります。<br /><br />

レポジトリーへのリンクは: [こちら](https://github.com/Jer-B/Ethernaut_Fallout_-spoil-)。
<br />
<br />
<br />

## Ethernaut 3. Coinflip

<br/>
<p align="center">
<img src="https://github.com/Jer-B/Ethernaut_Coinflip_-spoil-/blob/main/images/coinflip.png" width="900" alt="Ethernaut coinflip">
</p>
<br/>

- 目標は、`flip（）` 関数を呼び出すときに、コインがどの側に反転するかを 10 回正しく予想することです。<br /><br />

レポジトリーへのリンクは: [こちら](https://github.com/Jer-B/Ethernaut_Coinflip_-spoil-)。
<br />
<br />
<br />

## Ethernaut 4. Telephone

<br/>
<p align="center">
<img src="https://github.com/Jer-B/Ethernaut_Telephone_-spoil-/blob/main/images/Telephone.png" width="900" alt="Ethernaut Telephone">
</p>
<br/>

目標は、スマートコントラクトの所有者になることです。<br/>

- `Telephone`スマートコントラクトでは、`tx.origin` からのトランザクションでない場合、オーナーになる仕組みがあります。<br/>
- トランザクションの発生元を示すときに、`tx.origin` または `msg.sender` を使用するかどうかは問題です。<br/>
- `tx.origin` 変数は、トランザクションを開始した元の外部アカウントを参照しますが、`msg.sender` はユーザーから直接のトランザクションです。<br/><br />
  レポジトリーへのリンクは: [こちら](https://github.com/Jer-B/Ethernaut_Telephone_-spoil-)。
  <br />
  <br />
  <br />

## Ethernaut 5. Token

<br/>
<p align="center">
<img src="https://github.com/Jer-B/Ethernaut_Token_-spoil-/blob/main/images/token.png" width="900" alt="Ethernaut Token">
</p>
<br/>

目標は、コントラクトのすべての ERC20 トークンを手に入れることです。

- このコントラクトのミソは、`Solidity 0.6.0` の下で行われたことです。`0.8.0` では、数値の処理に `SafeMath` と呼ばれるライブラリを使用する必要があります。
- `SafeMath` がない場合、コンパイラバージョンが `0.8.0` 未満のすべての Solidity コントラクトには`アンダーフロー`と`オーバーフロー`の問題があります。
- 例：`uint` 型の整数で値が `20` の場合、`20 + 1` を行ったとしましょう。結果は`21` ではなく、`21` を超えて `1` を得ます。これはこの場合の `UintMax` です。
- つまり、合計供給量のすべてのトークンを持っている可能性があります。
- この問題を防ぐために `SafeMath` が使用されました。`0.8.0` 以降、Solidity にはデフォルトで組み込まれています。<br /><br />

レポジトリーへのリンクは: [こちら](https://github.com/Jer-B/Ethernaut_Token_-spoil-)。
<br />
<br />
<br />

## Ethernaut 8. Vault

<br/>
<p align="center">
<img src="https://github.com/Jer-B/Ethernaut_Vault_-spoil-/raw/main/images/vault_contract.png" width="700" alt="Ethernaut Vault">
</p>
<br/>

コントラクトを解除する目的は、`Bytes32` パスワードを見つけることです。

- ここでの解決策は、`private` 変数 `password` の値を見つけることです。

  レポジトリーへのリンクは: [こちら](https://github.com/Jer-B/Ethernaut_Vault_-spoil-).
  <br />
  <br />
  <br />

## Ethernaut 9. King

<br/>
<p align="center">
<img src="https://github.com/Jer-B/Ethernaut_King_-spoil-/raw/main/images/king_contract.png" width="700" alt="Ethernaut King">
</p>
<br/>

コントラクトの管理権を握ることが目標です。

- ここでの解決策は、賞金よりも多いエーテルをコントラクトに送ることです。簡単な説明は以下の通りです：
- これを行うには、`call`関数のみを使用できます。
- `transfer`や`send`は使用できません。コントラクトの`receive`関数を呼び出すと、2300 のガス上限のためにトランザクションがリバートされるからです。
- `call`関数にはこのガス上限がなく、エーテルをコントラクトに送るために使用できます。

  レポジトリーへのリンクは: [こちら](https://github.com/Jer-B/Ethernaut_King_-spoil-).
  <br />
  <br />
  <br />

## Ethernaut 10. Re-Entrancy

<br/>
<p align="center">
<img src="https://github.com/Jer-B/Ethernaut_ReEntrancy_-spoil-/raw/main/images/reentrant_contract.png" width="700" alt="Ethernaut King">
</p>
<br/>

目標は、契約の資金を空にすることです。

- - 何が起こるかというと、攻撃に使用される契約の残高に`value`を設定するために`donate`を呼び出す必要があります。
- その後、`withdraw`を呼び出して契約の中身を空にします。状態の変更が後で起こるため、`receive`関数が呼び出され、攻撃された契約の残高が`0.001eth`未満になるまで攻撃が繰り返されます。

  レポジトリーへのリンクは: [こちら](https://github.com/Jer-B/Ethernaut_ReEntrancy_-spoil-).
  <br />
  <br />
  <br />
