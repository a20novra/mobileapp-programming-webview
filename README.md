# Rapport

uppgift beskrivningen var ganska tydligt och man kunde göra allt steg efter steg, därför vill jag förklara hur jag gjorde uppgiften med tanke på uppgiftens punkter.
Första steget var att forka uppgiften eller projektet från Lenasys github vilken gick smidigt. Man klickar på fork knappen och sen github ge dig en specifik version av projektet som ligger på din github sen man kan bara kopiera länken och clone det på android studio. 

Första praktiska saken som jag gjorde var att byta min apps namn till något annat, vilken går att göra det om man kollar igenom den här adressen**res/values/strings.xml**. 

För att möjliggöra att appen få tillgång till internet man måste lägga till den här koden 
```
<uses-permission android:name="android.permission.INTERNET" />
```
Längst up i **AndroidManifest.xml** filen. 

Det fanns en TextView från början som jag ersatte det med en WebView. Sen jag ändrade min WebViews Id till my_webview. Höjden och bredden täckte hela skärmen eftersom de är satt på match_parent.  
```
 <WebView
        android:id="@+id/my_webview"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        />
```

För att skapa privat medlem man måste bara använda från begreppet **private** och sen data typen vilken var WebView och ett namn för variabeln som jag skrev det myWebView. Det enda viktiga punkt som man måste tänka på är att privata medlemmen måste skapas utanför funktioner, men inne i klassen. Sen in i onCreate funktion man deklarerar privata medlemmen. Det måste deklareras till id som jag har gett till WebView tidigare, vilken görs med hjälp av findviewbyid. 
```
  private WebView myWebView;
```
```
  WebView myWebView = (WebView) findViewById(R.id.my_webview);
```
Det går att visa webbsidor på en android app med hjälp webView, men som ni vet webbsidor använder från javascript. Javascript funktionen är inte aktiverat på appar men går att aktivera det med två rad koder i main activity filen. 
```
    WebSettings webSettings = mywebview.getSettings();
    webSettings.setJavaScriptEnabled(true);
```



Jag skapade en HTML sida för att kunna visa det när man klickar på internal web page. För att implementera `showExternalWebPage()` och `showInternalWebPage()` jag anvädne loadurl() funktionen. Måste säga att 
```
public void showExternalWebPage(){
}

public void showInternalWebPage(){
 }
```
var byggt och jag la in loadurl() funktionen och adressen som jag ville att just den knappen ska visa. För att kalla på de funktioner uppgiften gav oss en boolean funktion som innehöll två if satser. Den första if satsen var om vad ska hända om någon klickar på external knappen och den andra if satsen var om vad ska hända om någon klickar på internal knappen. Det är där som vi måste kalla vår funktioner. 
```
    if (id == R.id.action_external_web) {
           Log.d("==>","Will display external web page");
           showExternalWebPage();
           return true;
    }

```
```
     if (id == R.id.action_internal_web) {
            Log.d("==>","Will display internal web page");
            showInternalWebPage();
            return true;
     }
```

![](android.png)

