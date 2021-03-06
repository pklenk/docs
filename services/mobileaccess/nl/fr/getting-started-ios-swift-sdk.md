---

copyright:
  years: 2016
lastupdated: "2016-10-10"
---
{:shortdesc: .shortdesc}
{:screen: .screen}


# Configuration du SDK Swift iOS
{: #getting-started-ios}

{{site.data.keyword.amafull}} a rendu disponible un nouveau SDK Swift qui enrichit et améliore les fonctionnalités du SDK
{{site.data.keyword.amashort}} Objective-C existant, en facilitant l'authentification de votre application et en renforçant la protection
de vos ressources de back end. Instrumentez votre application Swift iOS avec le SDK {{site.data.keyword.amashort}}, initialisez le  the SDK et envoyez des requêtes à des ressources protégées et
non protégées.

{:shortdesc}

**Remarque :** Le SDK Objective-C communique des données de surveillance à la console de surveillance du service {{site.data.keyword.amashort}}. Si vous
êtes tributaire de la fonctionnalité de surveillance du service {{site.data.keyword.amashort}}, vous devez continuer à utiliser le SDK
Objective-C.

Bien que le SDK Objective-C soit toujours totalement pris en charge et soit encore considéré comme le SDK principal de
{{site.data.keyword.Bluemix_notm}} Mobile Services, il est envisagé de cesser de l'utiliser plus tard cette année et de le remplacer par ce nouveau SDK
Swift. 


## Avant de commencer
{: #before-you-begin}
Vous devez disposer des éléments suivants :
* Une instance d'une application {{site.data.keyword.Bluemix_notm}} qui est protégée par le service {{site.data.keyword.amashort}}. Pour plus d'informations sur la création d'un système de back end {{site.data.keyword.Bluemix_notm}}, voir [Initiation](index.html).
* Un projet Xcode. Pour plus d'informations sur la configuration de votre environnement de développement iOS, consultez le [site Web Apple Developer](https://developer.apple.com/support/xcode/).


## Installation du SDK client de {{site.data.keyword.amashort}}
{: #install-mca-sdk-ios}
Le SDK {{site.data.keyword.amashort}} est distribué avec CocoaPods, un gestionnaire de dépendances pour les projets iOS. CocoaPods télécharge automatiquement
des artefacts depuis les référentiels et les rend disponibles depuis votre application iOS.


### Installation de CocoaPods
{: #install-cocoapods}

1. Depuis une fenêtre de terminal, lancez la commande **pod --version**. Si CocoaPods est déjà installé, le numéro de version est affiché
et vous pouvez passer à la section suivante pour installer le SDK.

1. Si CocoaPods n'est pas installé, exécutez la commande :

```
sudo gem install cocoapods
```

Pour plus d'informations, reportez-vous au [site Web CocoaPods](https://cocoapods.org/).

### Installation du SDK client de {{site.data.keyword.amashort}} avec CocoaPods
{: #install-sdk-cocoapods}

1. Dans une fenêtre de terminal, naviguez jusqu'au répertoire racine de votre projet iOS.

1. Si vous n'avez pas encore initialisé votre espace de travail pour CocoaPods, exécutez la commande `pod init`.<br/>
CocoaPods crée automatiquement un fichier `Podfile`, dans lequel vous définirez les dépendances de votre projet iOS.

1. Editez le fichier `Podfile` et ajoutez la ligne suivante aux cibles requises.

	```
  use_frameworks!
  pod 'BMSSecurity'
	```

  **Astuce :** Vous pouvez ajouter `use_frameworks!` à votre cible Xcode au lieu du Podfile.

1. Enregistrez le fichier `Podfile` et lancez `pod install` depuis la ligne de commande. CocoaPods installe les dépendances
pertinentes et affiche les dépendances et nacelles ajoutées.<br/>

   **Important** : CocoaPods génère un fichier `xcworkspace`.  A partir de ce moment, vous devrez toujours ouvrir ce fichier pour travailler sur votre projet.

1. Ouvrez l'espace de travail de votre projet iOS. Ouvrez le fichier `xcworkspace` qui a été généré par CocoaPods. Exemple : pour `{your-project-name}.xcworkspace`, exécutez

	`open {your-project-name}.xcworkspace`

## Initialisation du logiciel SDK client de {{site.data.keyword.amashort}}
{: #init-mca-sdk-ios}

 Initialisez le logiciel SDK en passant le paramètre `applicationGUID`. En général, vous pouvez placer le code d'initialisation dans la méthode `application:didFinishLaunchingWithOptions` du délégué de l'application, bien que cet emplacement ne soit pas obligatoire.
 

1. Obtenez vos valeurs de paramètres de service. Ouvrez votre service dans le tableau de bord {{site.data.keyword.Bluemix_notm}}. Cliquez sur **Options pour application mobile**. Les valeurs `applicationRoute` et `tenantId` (qui portent également le nom d'`appGUID`) s'affichent dans les zones **Route** et **Identificateur global unique de l'application / ID titulaire**. Vous aurez besoin de ces valeurs pour l'initialisation du logiciel SDK et l'envoi de demandes à l'application de back-end.

1. Importez les structures requises dans la classe où vous comptez utiliser le SDK client {{site.data.keyword.amashort}}.

 ```Swift
 import BMSCore
 import BMSSecurity
 ```

1. Initialisez le SDK client {{site.data.keyword.amashort}}.

```Swift
	let tenantId = "<serviceTenantID>"
	let regionName = <applicationBluemixRegion>

	func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: 
		[UIApplicationLaunchOptionsKey: Any]?) -> Bool {

	let mcaAuthManager = MCAAuthorizationManager.sharedInstance
    mcaAuthManager.initialize(tenantId: tenantId, bluemixRegion: regionName)
      // possible values for regionName: BMSClient.Region.usSouth, BMSClient.Region.unitedKingdom, BMSClient.Region.sydney
	BMSClient.sharedInstance.authorizationManager = mcaAuthManager	
	return true
	}
 ```

* Remplacez la valeur `tenantId` par la valeur que vous avez obtenue depuis **Options pour application mobile**. Voir l'**étape 1**.
* Remplacez `<applicationBluemixRegion>` par la région dans laquelle votre application {{site.data.keyword.Bluemix_notm}} est hébergée. Pour afficher votre région {{site.data.keyword.Bluemix_notm}}, cliquez sur l'icône **Avatar**  ![icône Avatar](images/face.jpg "icône Avatar")  dans la barre de menu pour ouvrir le widget **Compte et support**. La valeur de région qui apparaît doit être l'une des suivantes : **US South**, **United Kingdom** ou **Sydney** et correspondre aux valeurs des constantes requises dans le code : `BMSClient.Region.usSouth`, `BMSClient.Region.unitedKingdom` ou `BMSClient.Region.sydney`.

   
## Envoi d'une demande à votre application back end mobile
{: #request}

Une fois que le SDK client {{site.data.keyword.amashort}} est initialisé, vous pouvez commencer à envoyer des requêtes à votre application back end
mobile.

1. Essayez d'envoyer depuis votre navigateur une requête à un noeud final protégé de votre application back end mobile. Ouvrez l'URL suivante : `{applicationRoute}/protected`, en remplaçant `{applicationRoute}` par la valeur **applicationRoute** extraite depuis **Options pour application mobile** (voir [Initialisation du logiciel SDK client de Mobile Client Access](#init-mca-sdk-ios)). Exemple : 

	`http://my-mobile-backend.mybluemix.net/protected
	`

	Le noeud final `/protected` d'une application back end mobile créée avec le conteneur boilerplate MobileFirst Services Starter est
protégé par {{site.data.keyword.amashort}}. Un message `Non autorisé` est renvoyé à votre navigateur car ce noeud final n'est
accessible qu'aux applications mobiles instrumentées avec le SDK client de {{site.data.keyword.amashort}}.

1. A l'aide de votre application iOS, envoyez une demande au même noeud final. Ajoutez le code ci-dessous après avoir initialisé `BMSClient` :

 ```Swift
	let customResourceURL = "<your protected resource absolute path>"
	let request = Request(url: customResourceURL, method: HttpMethod.GET)

	let callBack:BMSCompletionHandler = {(response: Response?, error: Error?) in
 if error == nil {
       	    print ("réponse :\(response?.responseText), aucune erreur")
     } else {
       	    print ("erreur : \(error)")
     }
	}

	request.send(completionHandler: callBack)
 ```
 {: codeblock}

1.  Lorsque votre demande aboutit, la sortie suivante figure dans la console Xcode :

 ```
 response:Optional("Bonjour, ceci est une ressource protégée de l'application back end mobile !"), no error
 ```
{: screen}
 
## Etapes suivantes
{: #next-steps}
Lorsque vous vous êtes connecté au noeud final protégé, les données d'identification n'ont pas été nécessaires. Pour obliger les utilisateurs à utiliser des données d'identification pour se connecter à votre application, vous devez configurer Facebook, Google ou l'authentification personnalisée.
  * [Facebook](facebook-auth-ios-swift-sdk.html)
  * [Google](google-auth-ios-swift-sdk.html)
  * [Authentification personnalisée](custom-auth-ios-swift-sdk.html)
