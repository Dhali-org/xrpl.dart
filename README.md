# xrpl.dart

xrpl.dart is a Dart package that provides bindings to the [`xrpl.js`](https://js.xrpl.org/) library, allowing developers to interact with the XRP Ledger in Dart applications.

## Features

This package is a work in progress, and so does not fully replicate the functionality of `xrpl.js`.

## Getting started

To use xrpl.dart in your Dart project, please follow these steps:
1. Add the following snippet to the bottom of the `body` of your `web/index.html`:
```html
  <script src="https://unpkg.com/xrpl@2.6.0/build/xrpl-latest-min.js"></script>
```

2.  Add it as a dependency in your pubspec.yaml file:

```yaml
dependencies:
  xrpl: ^0.0.1
```

3. Finally, run `dart pub get` to download the package.

## Usage

To use xrpl.dart, first import it into your code:

```dart
import 'package:xrpl/xrpl.dart;
```

You can then use the functionality provided by `xrpl.js` through the `xrpl.dart` bindings:

```dart
   var walletFromMneomicOptions = WalletFromMnemonicOptions(
      mnemonicEncoding: "bip39",
    );

    var wallet = Wallet.fromMnemonic(seed, walletFromMneomicOptions);

    Client client = Client("wss://s.altnet.rippletest.net:51233");

    client.connect().then((_) {
      client.fundWallet(wallet);

      String address = wallet!.address;
      client.getXrpBalance(address).then((balanceString) {
        print("Wallet balance: ${balanceString.toString()}");
      });
    });
```
**Please do not use this example for production code!**

## Contributing
Contributions to xrpl.dart are welcome! To contribute, please fork the repository and submit a pull request. Before submitting a pull request, please make sure that your code follows the [Dart Style Guide](https://dart.dev/guides/language/effective-dart/style).

## license
xrpl.dart is licensed under the MIT License. See the LICENSE file for more information.