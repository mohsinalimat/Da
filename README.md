# Da

[![Travis](https://img.shields.io/travis/iTofu/Da.svg?style=flat)](https://travis-ci.org/iTofu/Da)
[![CocoaPods](https://img.shields.io/cocoapods/v/Da.svg)](http://cocoadocs.org/docsets/Da)
[![CocoaPods](https://img.shields.io/cocoapods/l/Da.svg)](https://raw.githubusercontent.com/iTofu/Da/master/LICENSE)
[![CocoaPods](https://img.shields.io/cocoapods/p/Da.svg)](http://cocoadocs.org/docsets/Da)
[![LeoDev](https://img.shields.io/badge/blog-LeoDev.me-brightgreen.svg)](https://LeoDev.me)

🌟 Naughty flexible alert view above the navigation bar, like QQ's. Da is a part of [DaXia](https://github.com/iTofu/DaXia).

<!-- ![Da](https://raw.githubusercontent.com/iTofu/Da/master/DaDemoImage/DaDemoImage.png) -->

```
In me the tiger sniffs the rose.

心有猛虎，细嗅蔷薇。
```

Welcome to visit my blog：https://LeoDev.me



## Contents

* [Requirements](https://github.com/iTofu/Da#requirements)
* [Installation](https://github.com/iTofu/Da#installation)
* [Usage](https://github.com/iTofu/Da#usage)
* [Preview](https://github.com/iTofu/Da#preview)
* [ChangeLog](https://github.com/iTofu/Da#changelog)
* [Support](https://github.com/iTofu/Da#support)
* [License](https://github.com/iTofu/Da#license)



## Requirements

* iOS 8.0+
* Xcode 8.0+
* Swift 3.0+



## Installation

### CocoaPods

[CocoaPods](http://cocoapods.org) is a dependency manager for Cocoa projects. You can install it with the following command:

```bash
$ gem install cocoapods
```

> CocoaPods 1.1.0+ is required to build Da.

To integrate Da into your Xcode project using CocoaPods, specify it in your `Podfile`:

```ruby
use_frameworks!

target '<Your Target Name>' do
    pod 'Da'
end
```

### Manually

If you prefer not to use the aforementioned dependency manager, you can integrate Da into your project manually.



## Usage

* Quick Start:

  ```swift
  import Da

  func showAlertQuickly() {

      Da.showAlert(title: "温馨提示",
                   message: "您的账号已在其他设备登录，请您注意账号安全。",
                   cancelButtonTitle: "退出",
                   otherButtonTitles: nil)
  }
  ```

* Detailed:

  ```swift
  func showAlertDetailedly() {
  
      Da.hairColor = UIColor.orange
      let da = Da(title: "温馨提示",
                  message: "您的账号已在其他设备登录，请您注意账号安全。",
                  cancelButtonTitle: "退出",
                  otherButtonTitles: "重新登录", "修改密码")
      da.destructiveButtonIndexSet = Set(arrayLiteral: 0)
      da.destructiveButtonColor = UIColor.orange
      da.clickedHandle = { da, buttonIndex in
          print("clickedHandle: \(buttonIndex), \(da.cancelButtonIndex)")
      }
      da.willPresentHanlder = { da in
          print("willPresentHanlder, \(da.cancelButtonIndex)")
      }
      da.didPresentHanlder = { da in
          print("didPresentHanlder, \(da.cancelButtonIndex)")
      }
      da.willDismissHandler = { da, buttonIndex in
          print("willDismissHandler: \(buttonIndex), \(da.cancelButtonIndex)")
      }
      da.didDismissHandler = { da, buttonIndex in
          print("didDismissHandler: \(buttonIndex), \(da.cancelButtonIndex)")
      }
      da.show()
  }

  // And more see Da.swift...
  ```

* Resources:

  * [F.A.Q.](https://github.com/iTofu/Da/issues?q=)


## Preview

<!-- ![Da](https://raw.githubusercontent.com/iTofu/Da/master/DaDemoImage/DaDemoImageInfo.png)
---
![Da](https://raw.githubusercontent.com/iTofu/Da/master/DaDemoImage/DaDemoImageSuccess.png)
---
![Da](https://raw.githubusercontent.com/iTofu/Da/master/DaDemoImage/DaDemoImageWarning.png) -->


## ChangeLog

### V 0.0.4

* Bug fixed.

### V 0.0.3

* Public some properties:

  ```swift
  public static var titleFont: UIFont   = UIFont.systemFont(ofSize: 20.0)
  public static var messageFont: UIFont = UIFont.systemFont(ofSize: 16.0)
  public static var buttonFont: UIFont  = UIFont.systemFont(ofSize: 18.0)
  ```

### V 0.0.2

* Improve.

### V 0.0.1

* Hello World!



## Support

* If you have any question, just [commit a issue](https://github.com/iTofu/Da/issues/new).

* Mail: `echo bGVvZGF4aWFAZ21haWwuY29tCg== | base64 -D`

* Blog: https://LeoDev.me

* Donations:

  * PayPal:
  
    [![Donate](https://www.paypalobjects.com/en_US/i/btn/btn_donate_SM.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_donations&business=leodaxia@gmail.com&item_name=leodaxia@gmail.com)
  
  * Alipay or Wechat Pay:
  
    <img src="https://cdnqiniu.leodev.me/donate.png?v=1" alt="Donate with Alipay or Wechat Pay" title="Donate with Alipay or Wechat Pay" width="320"/>
    
  Please note: donation does not imply any type of service contract.


## License

Da is released under the [MIT License](https://github.com/iTofu/Da/blob/master/LICENSE).
