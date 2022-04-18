# ROOM
#Dependances:
[1.] ext {room_version = "2.3.0"}

[2.]
implementation "androidx.room:room-runtime:$room_version"
kapt "androidx.room:room-compiler:$room_version"

// optional - Kotlin Extensions and Coroutines support for Room
implementation "androidx.room:room-ktx:$room_version 
                  ***_____***

Un moyen simple d'utiliser une [DB] dans une application Android consiste à utiliser une bibliothèque appelée [Room].
[Room] est ce qu'on appelle une bibliothèque [ORM (Object Relational Mapping)], qui, comme son nom l'indique, 
mappe les tables d'une [Relational DB] à des objets utilisables dans le code Kotlin.

# Create an entity
Lorsque vous travaillez avec [Room], chaque [table] est représentée par une [class].
celles-ci sont souvent appelées  [model classes ou entities]

Enfin, pour que [Room] reconnaisse cette classe comme quelque chose qui peut être utilisé pour 
définir des tables de [DB], vous devez ajouter une annotation [@Entity]

# Define the DAO
La prochaine classe que vous devrez ajouter pour intégrer [Room] est le [DAO].
[DAO (Data Access Object)] et est une classe Kotlin qui permet d'accéder aux data.

Plus précisément, le [DAO] est l'endroit où vous incluriez des fonctions de lecture et de manipulation de données.
Appeler une fonction sur le [DAO] équivaut à exécuter une [commande SQL] sur la [DB]. 


# Define the ViewModel
Vous pouvez maintenant instancier un BusScheduleViewModelFactory objet avec BusScheduleViewModelFactory.create(),
afin que votre modèle de vue puisse être conscient du cycle de vie sans que votre fragment ait à le gérer directement.


# Create database class and pre-populate database
Maintenant que vous avez défini les modèles, [DAO] et un [viewModel] pour que les fragments accèdent au DAO,
vous devez encore dire à [Room] quoi faire avec toutes ces classes. C'est là que la [AppDatabase] classe entre en jeu

Dans votre application, les [AppDatabase] besoins de

[1.] Spécifiez les [entities] définies dans [DB].
[2.] Fournir un accès à une seule instance de chaque classe [DAO].
[3.] Effectuez toute configuration supplémentaire, telle que le pré-remplissage de [DB]

[AppDatabase] permet aux autres classes d'accéder facilement aux classes DAO.
Lorsque vous utilisez une [AppDatabase] classe, vous voulez vous assurer qu'une seule instance de [DB] existe pour éviter
les conditions de concurrence ou d'autres problèmes potentiels. 