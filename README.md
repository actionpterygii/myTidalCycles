# TidalCyclesをつかう

## 導入
- ぐぐってでてきたのでやったけど動かなかったのでいろいろしたらよくわからんけど動いた
- macOS High Sierra 10.13.6
- `ghci`,`Haskell Pratform`,`stack`,`Atom`,`SuperCollider`はいれてなかった
- Haskell知らず
### わたしのしたこと
- HomeBrewははいっているのでアップデート
- [ここ](https://pages.tidalcycles.org/tidal-bootstrap/)から`tidal-bootstrap`ダウンロード
  - zip展開
    - `tidal-bootstrap.command`ダブルクリック
      -　結構待って完了
    - `install-superdirt-quark.scd`ダブルクリック
      - 書いてある`include("SuperDirt")`の行にいって command + enter
- Atomは入れていなかったがなんか入っていた(どっかで何かが入れていた雰囲気)
  - Atom → Preferences... → install から`tidalcycles`を探しinstall
- 入っているSuperColliderを開き
  - `SuperDirt.start`と書き、その行にいって command + enter
- `example.tidal`なファイルを作成してAtomで開く
  - サンプルであった`d1 $ sound "bd sn"`入力
  - Packages → TidalCycles → Boot TidalCycles
    - ここらでエラー 
      - `Variable not in scope: p :: Integer -> t`
      - `Variable not in scope: sound :: [Char] -> t0`
      - `Perhaps you meant ‘round’ (imported from Prelude)`
- vscodeでも`TidalCycles for VSCode`なる拡張機能があるためやってみるも鳴らず
  - Atomのときにつくってファイル開きその行にいって shift + enter
  - ここらでエラー
    - `error: Variable not in scope: d1 :: t0 -> t`
    - `Uncaught Error: This socket has been ended by the other party` ←Atomかも
- Atomもvscodeも設定から`Ghci Path`を
  - `stack ghci`とか`stack exec ghci`とかするも鳴らずもどす
  - vscodeは`Use Stack Ghci`チェックも鳴らず
- vscodeではエラーがでずに鳴らない場合も
- SuperCollider → Language → Recompile Class Library とかもした
- どっかにあった`cabal install tidal`したら鳴った

### 最終
- The Glorious Glasgow Haskell Compilation System, version 8.6.5
- stack 1.9.3 x86_64
- SuperCollider 3.10.2
- Atom 1.37.0 x64
  - tidalcycles 3.0.0 
