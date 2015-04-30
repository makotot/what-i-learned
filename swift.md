# [Swift](https://developer.apple.com/swift/)

SwiftはiOSとOSXのための新しいプログラミング言語。
iOSとOSX向けのアプリケーション開発に使用する。

> モダン、安全、高速、インタラクティブ
>  http://ja.wikipedia.org/wiki/Swift_%28%E3%83%97%E3%83%AD%E3%82%B0%E3%83%A9%E3%83%9F%E3%83%B3%E3%82%B0%E8%A8%80%E8%AA%9E%29


---


## StyleGuide

- [Github](https://github.com/github/swift-style-guide)
- [raywenderlich](https://github.com/raywenderlich/swift-style-guide)
- [iPhone - Swiftコーディング規約@Wantedly  - Qiita](http://qiita.com/susieyy/items/f71435cc962e70d81b37)


---


## [Cocoa](http://ja.wikipedia.org/wiki/Cocoa)

OSX用アプリケーションを構築するためのAPI。

- OS機能などサービス層 -> Foundation
- GUIパーツの集合 -> AppKit


---

## Structure

### AppDelegate.swift

アプリケーション全体の管理？

- [AppDelegate.swift って何なのさ | Ryo's Hacks](http://ryoshacks.jp/programming/swift/appdelegate/)
- [[iOS] AppDelegateを綺麗に保つ4つのテクニック - Qiita](http://qiita.com/nori0620/items/66ebc623f63fc3f0ca20)

### ViewController.swift

Viewの管理？

- [Single View Application Project - ViewController.swiftの解説 - Qiita](http://qiita.com/kilhyungdoo/items/faf19ffa38eb8a1e6756)
- [SwiftでViewControllerを使う - Qiita](http://qiita.com/web_chiro/items/66dc637463f98716bfa5)


### info.plist

アプリケーションで共通の設定を行う設定ファイル。

- [Info.plist - iPhoneアプリ開発の虎の巻](http://iphone-tora.sakura.ne.jp/iphone_infoplist.html)


---

## Syntax

### @NSApplicationMain

- [osx - What is use of @NSApplicationMain in swift programming project in xcode - Stack Overflow](http://stackoverflow.com/questions/27469436/what-is-use-of-nsapplicationmain-in-swift-programming-project-in-xcode)
- [Swift - Xcode 6.1-Beta2 における変更点 - Qiita](http://qiita.com/dankogai/items/fe86f43a0158c13082ad#2-4)


### var

値が変更可能な変数。


### let

値が変更不可な定数。

- [変数と定数 | Swift言語を学ぶ](http://tea-leaves.jp/swift/content/%E5%A4%89%E6%95%B0%E3%81%A8%E5%AE%9A%E6%95%B0)


### 型推論

変数とか定数の型が明確な場合、型を明記しなくても自動的に型推論する。

- [型推論 - Wikipedia](http://ja.wikipedia.org/wiki/%E5%9E%8B%E6%8E%A8%E8%AB%96)


### 型

- [Swiftの変数と型について | イリテク](http://iritec.jp/objective-c/9105/)


### 関数

```swift
func Foo () {
}
```

- [関数 | Swift言語を学ぶ](http://tea-leaves.jp/swift/content/%E9%96%A2%E6%95%B0)


### class


#### init

イニシャライザ。インスタンス生成時に必ず呼ばれるメソッド。

```swift
class Foo {

  init () {
    ...
  }
}
```

- [Swift クラス(Class) 初期化(イニシャライザ) 破棄(デイニシャライザ) - Codable Tech Blog ](http://blog.codable.co.jp/entry/2014/11/04/171935)



### @IBOutlet, @IBAction

storyboardから認識されるようになる。

- [swiftでIBOutlet, IBAction - Qiita](http://qiita.com/jazzsasori/items/6053e1467772b7ff9783)
- [IBOutletとIBAction：関連付けでラクラクパーツを配置しよう | iPhoneアプリ開発大百科](http://iphone-app-program.com/newapp/iboutlet-and-ibaction/ibbas/)


### awakeFromNib

- [Cocoa探検隊 awakeFromNibの落し穴](http://www013.upp.so-net.ne.jp/tanken/Tanken/no4_PitfallOfNib.html)
- [Objective-C - awakeFromNibとinitWithFrameとinitWithCoderの使い方 - Qiita](http://qiita.com/reikubonaga/items/cb52dea471cfe1640773)


### Selector

別のメソッドから実行されることになるメソッド？

- [Developer Learning Solutions: Swift - Using Selector in Swift](http://weimenglee.blogspot.jp/2014/09/swift-using-selector-in-swift.html)
- [@selector() in Swift? - Stack Overflow](http://stackoverflow.com/questions/24007650/selector-in-swift)
- [Swiftで、セレクタ(@selector)を指定する。](http://www.jagaimopotato.com/blog/ios-application-development/swift-selector-call-3270.html)



---

## Event

`viewDidLoad`が呼ばれるのはインスタンス化された直後。

- [今更だけどiOSアプリでviewDidLoadとかviewWillAppearとかが呼ばれるタイミングをまとめてみる - (ﾟ∀ﾟ)o彡 sasata299's blog](http://blog.livedoor.jp/sasata299/archives/52029262.html)
- [viewDidLoad,viewWillAppear,viewDidAppear,viewWillDisappearなど | 3urprise.com](http://smileapps.sakura.ne.jp/blg/?p=931)



---

## Storyboard

画面遷移をGUIでつくれるもの？

- [[iOS]これからiOSアプリを作る方向け Storyboardで画面遷移を作る ｜ Developers.IO](http://dev.classmethod.jp/smartphone/iphone/remind-storyboard/)



---

## Links


- [[iOS][Mac] Swift を学べる記事のまとめ ｜ Developers.IO](http://dev.classmethod.jp/smartphone/iphone/learn-swift/)
- [Swiftプロジェクトに入る前に読んだことまとめ - Qiita](http://qiita.com/reikubonaga/items/2a754c02534f8e7f97c2)
- [Swift by example ](http://brettbukowski.github.io/SwiftExamples/)
- [matteocrippa/awesome-swift](https://github.com/matteocrippa/awesome-swift)
- [Wolg/awesome-swift](https://github.com/Wolg/awesome-swift)
- [Swift | Swift言語を学ぶ](http://tea-leaves.jp/swift/)


### Guide

- [Swift (プログラミング言語) - Wikipedia](http://ja.wikipedia.org/wiki/Swift_(%E3%83%97%E3%83%AD%E3%82%B0%E3%83%A9%E3%83%9F%E3%83%B3%E3%82%B0%E8%A8%80%E8%AA%9E))
- [Ultimate Guide to Learning Swift in One Day](https://www.airpair.com/swift/complete-guide-to-swift)


### Tutorial

- [Free Swift video tutorials on iOS and Mac development | Swift Video Tutorials](http://www.swiftvideotutorials.com/)
- [SoSoSwift - Easily The Biggest Set of Swift Programming Tutorials On The Internet.](http://www.sososwift.com/)


### Demo

- [supertommy/swift-status-bar-app-osx](https://github.com/supertommy/swift-status-bar-app-osx)
- [Swift - ステータスバーに常駐するアプリケーション - Qiita](http://qiita.com/arthur87/items/1998541004853d171088)
- [How I used Swift to build a Menubar App for OSX - John Mullins](http://www.johnmullins.co/blog/2014/08/08/menubar-app/)
- [yene/Simple-Duration](https://github.com/yene/Simple-Duration)



