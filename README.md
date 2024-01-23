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

Introductory level.<br />
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

The goal is to become the Owner of the smart contract to be able to steal all the funds in it.<br />
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

- The best hint is in the presentation image of the problem. <br />
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

The goal is to guess 10 times the right side on which the coin is gonna flip when calling the `flip()` function.<br />
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
- The `tx.origin` global variable refers to the original external account that started the transaction while `msg.sender` is a direct transaction from an user.<br />
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

これは導入的なレベルである。<br />

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

目標は、そのスマートコントラクトのオーナーになり、中にあるすべての資金を奪うことです。<br />

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
  最も役立つヒントは、問題のプレゼンテーション画像にあります。<br />

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

- 目標は、`flip（）` 関数を呼び出すときに、コインがどの側に反転するかを 10 回正しく予想することです。

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
- `tx.origin` 変数は、トランザクションを開始した元の外部アカウントを参照しますが、`msg.sender` はユーザーから直接のトランザクションです。<br/>
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
- この問題を防ぐために `SafeMath` が使用されました。`0.8.0` 以降、Solidity にはデフォルトで組み込まれています。

レポジトリーへのリンクは: [こちら](https://github.com/Jer-B/Ethernaut_Token_-spoil-)。
<br />
<br />
<br />
