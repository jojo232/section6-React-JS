# Pops
### コンポーネント
・画面要素の1単位。大(1画面)から小(1つもテクストボックス)まで様々。
### Props
・コンポーネントに渡される引数的なもの</br>
### State
・各コンポーネントが持つ状態。Stateが変更されると再レンダリングされる。</br>
<img width="100" alt="スクリーンショット 2022-08-26 17 33 48" src="https://user-images.githubusercontent.com/65487059/226085749-6514db4a-30bb-45b8-bddc-01da309bff26.jpeg"></br>
<img width="100" alt="スクリーンショット 2022-08-26 17 33 48" src="https://user-images.githubusercontent.com/65487059/226090825-fba68743-ac68-49f0-864f-5046c3ee66bc.jpeg">

# 再レンダリングが起きる条件
・　stateが更新されたコンポーネントは再レンダリング　　<br>
・　propsが変更されたコンポーネントは再レンダリング<br>
・　再レンダリングされたコンポーネント配下の子要素は再レンダリング<br>
### （親の再レンダリングを起こさないには、memoで囲ってあげる必要がある）
### 同じものを使い回す、useCallback


# 最初に作成すること
- 名前は頭大文字のApp、引数はなしで、矢印を書いて、ブラケットを書いていく
- まずは空の要素を作っていく、retnrnでnullを返却する。- 
- これでnullの値を返す、Appの値が完- 成
　- ではこのAppを画面に反映して- いく
- 画面に反映する場合は、先程- インポートしたReact-Domのライブラリーの中身の
- renderという関数を使用し- ていく、render関数の引数の一行目にAppを
- コンポーネントとしてレンダ- リングしていく、HTMLのタグのように/で閉じる
- 2つ目の引数にどこに反映- するかを記載する、JSで使用した(ID)を取得する。
- divのところでIdはroo- tを指定しているのでrootを反映させる。
- ReactDom.render(<App />, document.getElementById("root"));　これでReact開発の基盤が出来上がった

# JSX記号
- ではJsx記号を使用して画面に要素を表示していく
- nullを消して(h1)タグを記載
- JSの中でretnrnしてその中でHTMLのタグを書ことを、JSX記号をいう
- 文字を増やしていく場合は、retnrnの中を()で閉じる
- retnrnの中に記載する時は<></>で囲わないといけない！！

# component
- Reactではいろんなファイルにコンポーネントとして分けて管理する
-　他のファイルでも使用できるようにexport　default App(関数名)
- Appを使用していきたいので　import App from "./App"(同じ階層にある)
- このように他のファイルで画面のレンダリング部分を作成してexportして
- 他のファイルからimportすることでそれをコンポーネントとして使用可能


# イベントの扱い方はstyleの扱い方を知ろう
- ボタンをクリックして時の関数を書いていく
- 全段で関数を作成してbuttonに関数を記載していく
　- h１タブに直接記載、{{}} 外側はJS、中側はJSのオブジェクトのナミかっこです。
- オブジェクトととしてstyleを記載していく
- 色しての時は''(文字列でかっこてあげるように気をつける)
- 他にも変数名をしていしてstykeを書いていく
- Reactの場合は、キャメルケースで記載する

# popsとは、先程分けたコンポーネントに対して渡す引数のようなものだと
- コンポーネントとして画面の要素を切り出しても、通常時は黒文字だけど、異常の場合は赤文字表示
- ある程度動的にコンポーネントを使用できるようにpropsで条件を渡していく
- (例)、文字の色を一個ずつ返るのがめんどくさい
- 従って、この文章のところをコンポーネント化して、色と文章をpropsとして受け取るようにしていきたい
- propsで条件を渡して動的に変わるコンポーネントにしていく
- propsを渡すには、渡す方と渡される方にそれぞれコードを修正いく必要がある
- タグの中にpropsとして渡したい名称を書いていく、今回は色を渡していきたいので
- colorとする、渡す内容を=で書いてあげる、message= "お元気ですか？"propsで渡す
- colofullmessage(コンポーネント)に対して、適当な名前をつけて=で要素を渡していく
- コンポーネントに対して、propsを渡していくことが可能、

- componentの引数に、　App.jsでpropsを指定したのでそれを引数に記載してあげる。
- 名前はなんでもいいけど、propsにしたほうがいいので
- buleの部分にpropsを渡していく、props.color
- {props.message}
- props.Chirudrenをしているすると<>あああ</>　カッコないで閉じた文字が記載される

- propsがたくさんあるので、分割代入を使ってコードをスッキリさせる
- const { color, childre } = props;
- JSはオブジェクトでプロパティ名と当てはめる値が同じ名前の時は記載しなくて良い

# Stateとは
- それぞれのコンポーネントが持っている状態、可変状態のこと
- 条件によって動的に変わる部分をステートとして定義し、状態の画面を表示する
- useStateはReactの中に入っている、分割代入ですね、
- 実際に使用していく変数を設定していく、useStateの中から配列の分割代入から取り出します
- 動的に変わるnumとそれを更新していくsetnumという関数を設定していく、命名規則はない、なんでもいい
- 1つ目にステートの変数名、2つ目にステートを更新していく変数名を書いていく
- useStateに中で初期値(引数)を設定することができる、今回は初期値0
- numの変数に0が設定されているか確認する
- numという数値を動的に更新していきたい、ボタンをクリックするとカウントアップする機能を実装していく
- このアロー関数の中でステートを更新する処理を入れていきたいと思います
- ステートを更新する場合は、2つ目で設定した値を使用していく
- numに更新したい値をsetNum();引数に入れていく
- 現在のステートにボタンを押すことにより、カウントが1つずつ増加していく

# 再レンダリング(useEffect)　//
- (p)タグも文字がボタンを押すを表示になったり、非表示になったりする
- ボタンでon/offを切り替える
- 表示を持たせたい場合は、状態を扱うので、Stareを定義する
- 表示、非表示なのでtrue/fales
- 1つ目の変数がtrueの場合は、顔文字をレンダリングしていきたい
- 論理演算子で使用したことが生きていく
- まずはフラグを判定するので、{}(ブラケット)使用する
- １つ目の変数でレンダリングの判定をしていくので
- on変数がtrueの場合だけ、顔文字を表示する
- {on && ^_^}
- &&の左の要素にtrueの場合に右を返す
- useStare(false)にすると左側にfalseが代入されるので、何も表示されない

- ボタンをクリックしたときに、true/falseに切り替えるように設定していく
- ボタンにonClick処理を記載していく、使用する関数を定義していく
- 新しく作成した関数をアロー関数で記載して、2つ目の変数(ステート更新)を入れる
- 現在設定されている値を反対の値を指定したいので(!on);と記載する　！=逆
- 新しく作成した関数をonClickの引数に割り当てていく- 
