# IAPurchaseManager
Swift In-App Purchase Manager for iOS 

Easy-to-use a singleton class that supports non-renewable in-app purchases. 
It's super cool because</br>
1) it's written in Swift</br>
2) it uses blocks!

<h2>Setup</h2>
Just drag <b>IAPManager.swift</b> to your project.

<h2>Making a purchase</h2>

If you want to make a purchase, all you need to do is to call a method:
```swift
  IAPManager.sharedManager.purchaseProductWithId(productId) { (error) -> Void in 
    if error == nil {
      // successful purchase!
    } else {
      // something wrong.. 
    }
}
```

You can call <b>purchaseProductWithId</b> without first loading products info because inside purchaseProductWithId it'll load it if needed. So just call <b>purchaseProductWithId</b> whenever you want to make a purchase. 

But if you need to get all products info, you can load it by calling:
```swift
  IAPManager.sharedManager.loadProductsWithIds(productIds) { (error) -> Void in }
```

<h2>Restore transactions</h2>

To restore transactions call:
```swift
  IAPManager.sharedManager.restoreCompletedTransactions { (error) -> Void in }
```

<h2>Details</h2>
All completed transactions are saved to a file:
```swift
data.writeToFile(purchasedItemsFilePath(), options: .AtomicWrite | .DataWritingFileProtectionComplete, error: &error)
```

</br>
</br>
If you want to add validation, keychain support or some other features, feel free to send me pull requests!
