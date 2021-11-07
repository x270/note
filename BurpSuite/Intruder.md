# Intruder

## Target
Intruderに送ったリクエストに応じたHost,Portが自動的に入るので、特に何もしなくてよい。

## Positions
検査対象のパラメータの位置を設定する。  
Intruderに送った時点で、ある程度自動的に設定される。  
Add§ボタンで選択している箇所を検査対象にする。
Clear§ボタンで一括解除可能。  
Ctrl＋Zキーで前の状態へ戻せる。
- `§hoge§`：パラメータの値hoge自体を検査文字列へと置換していく
- `hoge§§`：パラメータの値hogeの後ろに検査文字列を追加する

### Attack type
- `Sniper`：`§`で指定した箇所1つずつに対して順々に検査文字列を適用。  
Payload Setは１つしか指定できない。
- `Battering ram`：`§`で指定した箇所すべてに対して一気に検査文字列を適用。  
Payload Setは１つしか指定できない。
- `Pitchfork`：`§`で指定した箇所それぞれに適用する検査文字列をPayload Optionsで指定。  
`§`で指定した数だけ、Payload Setを指定する必要がある。  
指定した複数のPayload Setの件数が一致しない場合、少ない方のSetが枯渇した時点で終了。
  - id=Alice&pass=hoge
  - id=Bob&pass=fuga 
- `Cluster Bomb`：`§`で指定した箇所それぞれに検査文字列を指定できるが、１つ目のパラメータが終わってから次を試行。  
`§`で指定した数だけ、Payload Setを指定する必要がある。  
指定したPayload Setの全組み合わせが試行される。
  - id=Alice&pass=hoge
  - id=Alice&pass=fuga <- Aliceは固定したまま、次の検査文字列fugaを使用
  - id=Bob&pass=hoge <- passが一巡したので、idをAliceの次のBobへ切り替え
  - id=Bob&pass=fuga



