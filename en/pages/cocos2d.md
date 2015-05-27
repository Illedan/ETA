# Cocos2d for Xamarin

## Seal game

This is going to be a 2d platform game. The goal is to avoid balls and ice bears in order to escape from a circus. It`s a game with no end. Pictures are comming.

## Menu

For my Seal-game I wanted a menu looking like a Circus, where the buttons were circus objects.

Example: ( **Shop** )

<label for="name" align:"middle"  id="name_label">Normal state:</label>

<img align="middle" src="../pages/uploads/images/circusshop.png" alt="Drawing" style="width: 100px;"/>

<label for="name" align:"middle"  id="name_label">Clicked state:</label>

<img  src="../pages/uploads/images/clickedcircusshop.png" alt="Drawing" style="width: 100px;"/>


Add images to your Content folder and add code to load the images as Selected- and normal-image of a button.
```csharp
ShopButton = new CCMenuItemImage ();
ShopButton.NormalImage = new CCSprite ("circusshop");
ShopButton.SelectedImage = new CCSprite ("clickedcircusshop");
ShopButton.Scale = 0.3f;
ShopButton.PositionX = 100;
ShopButton.PositionY = 300;
```

Next is the handling of clicks:
```csharp
ShopButton.Target = OpenShop;
//----
private void OpenShop(Object c){
  var transition = new CCTransitionScene (0.1f, new ShopScene (Window));
  var transitionToGame = new CCTransitionRotoZoom (0.7f, new ShopScene (Window));
  Window.DefaultDirector.ReplaceScene (transition);
}
```
