# Notary Tools

![notarize](https://user-images.githubusercontent.com/22433243/153662864-191f43f7-359f-41c9-b80d-88c617c5d2d6.png)

☞ Github Action to **notarize** and **staple** macOS applications or packages. 

It does this by submitting your built `.app`, `.pkg` or `.dmg` file to Apple's notary service (by using `xcrun notarytool`) and staple the product (by using `xcrun stapler`).

[Reference]([notarytool](https://developer.apple.com/documentation/security/notarizing_macos_software_before_distribution/customizing_the_notarization_workflow#3087734))

## 📚 Usage

### Simple value

```yaml
runs-on: macos-latest
steps:
  uses: GuillaumeFalourd/notary-tools@v1
  with:
    product_path: "path/to/file.app" # or .pkg or .dmg
    apple_id: ${{ secrets.APPLE_ID }}
    password: ${{ secrets.PASSWORD }}
    team_id: ${{ secrets.TEAM_ID }}
    staple: 'false'
    keychain_profile: 'my-keychain-profile'
    xcode_path: '/Applications/Xcode_13.3.app'
```

## ▶️ Action Inputs

Field | Mandatory | Observation
------------ | ------------  | -------------
**product_path** | YES | Path to the product to notarize. </b> e.g: `path/to/product`
**apple_id** | YES | [notarytool](https://developer.apple.com/documentation/security/notarizing_macos_software_before_distribution/customizing_the_notarization_workflow#3087734) --apple-id parameter
**password** | YES | [notarytool](https://developer.apple.com/documentation/security/notarizing_macos_software_before_distribution/customizing_the_notarization_workflow#3087734) --password parameter
**team_id** | YES | [notarytool](https://developer.apple.com/documentation/security/notarizing_macos_software_before_distribution/customizing_the_notarization_workflow#3087734) --team-id parameter.
**keychain_profile** | YES | [notarytool](https://developer.apple.com/documentation/security/notarizing_macos_software_before_distribution/customizing_the_notarization_workflow#3087734) --keychain-profile parameter.
**staple** | NO | Whether to staple the notarized product (default `true`).
**xcode_path** | NO | Path of the Xcode version to use (default `/Applications/Xcode_13.2.1.app`).

## 🤝 Contributing

☞ If you're interested in contributing to this repository, please follow the [guidelines](https://github.com/GuillaumeFalourd/notary-tools/blob/main/CONTRIBUTING.md)

## 🏅 Licensed

☞ This repository uses the [Apache License 2.0](https://github.com/GuillaumeFalourd/notary-tools/blob/main/LICENSE)

<!-- ### Contribuidores

<a href="https://github.com/GuillaumeFalourd/notary-tools/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=GuillaumeFalourd/notary-tools" />
</a>

(Criado com [contributors-img](https://contrib.rocks)) -->
