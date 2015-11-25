![Format - a Swift Formatter Kit](https://cloud.githubusercontent.com/assets/889949/11390954/ee7607b6-934e-11e5-9754-b1cdb12f27d9.png)

[![Build Status](https://travis-ci.org/marmelroy/Format.svg?branch=master)](https://travis-ci.org/marmelroy/Format) [![Version](http://img.shields.io/cocoapods/v/Format.svg)](http://cocoapods.org/?q=Format)
[![Carthage compatible](https://img.shields.io/badge/Carthage-compatible-4BC51D.svg?style=flat)](https://github.com/Carthage/Carthage)

# Format
A Swift 2.0 formatter kit. Simple formatting syntax for decimal numbers, currency, addresses, ordinal numbers and hexadecimal colors.

## Usage

Import Format at the top of the Swift file with the content you would like to format.

```swift
import Format
```

## Number Formatting

Format provides a formatting extension for all number types. To format an Int to two decimal places:
```swift
let formattedNumber = 45.format(Decimals.Two) // 45.00
```

You can apply any of these formatters on any number type:
```swift
Decimals.Three // 10.123
Currency.USD // $10.12
General.Ordinal // 10th
General.SpellOut // ten point one two three
General.Distance // 30 feet
```

Please note that the distance formatter assumes the number represents the distance in meters before converting and formatting it to the current locale's preferred unit.

## Address Formatting

Different cultures have [different ways of displaying addresses](https://en.wikipedia.org/wiki/Address_(geography)#Address_format). Format includes an extension on CLPlacemark that converts the addressDictionary to a formatted string in the current locale.

```swift
let address = placemark.format()
```

To format a custom address (all fields are optional strings):

```swift
let address = AddressFormatter().format(street, city: city, state: state, postalCode: postalCode, country: country, ISOCountryCode: ISOCountryCode)
```

## Color Formatting

Format can help you convert hexadecimal colors from the web to UIColors you can work with.

```swift
let color = ColorFormatter().format("2ba134")
```

In case of an error, the color will default to black if the string is empty or white if the string is invalid.

### Setting up with Carthage

[Carthage](https://github.com/Carthage/Carthage) is a decentralized dependency manager that automates the process of adding frameworks to your Cocoa application.

You can install Carthage with [Homebrew](http://brew.sh/) using the following command:

```bash
$ brew update
$ brew install carthage
```

To integrate Format into your Xcode project using Carthage, specify it in your `Cartfile`:

```ogdl
github "marmelroy/Format"
```

### Setting up with [CocoaPods](http://cocoapods.org/?q=PhoneNumberKit)
```ruby
source 'https://github.com/CocoaPods/Specs.git'
pod 'Format', '~> 0.1'
```
