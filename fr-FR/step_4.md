## Compter les étoiles

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
Les jeux affichent souvent des informations d'état telles qu'un score. Tu montreras le nombre d'étoiles collectées jusqu'à présent.
</div>
<div>
![La vue Game affichant une variable "étoiles" sur le canevas.](images/counting-stars.gif){:width="300px"}
</div>
</div>

Un GameObject Unity peut avoir plusieurs scripts. Tu ajouteras un nouveau script à Player pour stocker et afficher le nombre d'étoiles qu'il a.

Le joueur doit garder une trace du nombre d'étoiles qu'il a collectées, tu peux le faire avec une variable.

--- task ---

Sélectionne le **Player** et dans Inspector clique sur **Add Component** et crée un nouveau script appelé `JoueurEtoile`. Ouvre ton nouveau script dans l'éditeur de code et crée une nouvelle variable appelée `étoiles` :

--- code ---
---
language: cs filename: StarPlayer.cs line_numbers: true line_number_start: 5
line_highlights: 7
---
public class StarPlayer : MonoBehaviour
{ public int stars = 0; // An integer whole number // Start is called before the first frame update void Start()
    { --- /code ---

Enregistre ton script et reviens à l'éditeur Unity.

--- /task ---

Le script `ControlleurEtoile` doit mettre à jour la variable `étoiles` sur le joueur à chaque fois qu'une étoile est collectée.

--- task ---

Ouvre ton script `ControlleurEtoile` et ajoute du code pour augmenter le nombre d'étoiles du joueur de 1 à chaque fois qu'une étoile est collectée.

Le paramètre `other` de la méthode `OnTriggerEnter` est défini sur le GameObject qui est entré en collision avec l'étoile. Tu peux l'utiliser pour accéder à la variable `étoiles` de `JoueurEtoile` :

--- code ---
---
language: cs filename: StarController.cs - OnTriggerEnter(Collider other) line_numbers: true line_number_start: 21
line_highlights: 26, 27
---

    void OnTriggerEnter(Collider other)
    {
        // Check the tag of the colliding object
        if (other.CompareTag("Player"))
        {
            StarPlayer player = other.gameObject.GetComponent<StarPlayer>();
            player.stars += 1; // Increase by 1
            AudioSource.PlayClipAtPoint(collectSound, transform.position);
            gameObject.SetActive(false);
        }
    }
--- /code ---

Enregistre ton script et reviens à l'éditeur Unity.

--- /task ---

--- task ---

**Test :** Exécute ta scène et collecte les trois étoiles. Regarde la variable publique `étoiles` dans la fenêtre Inspector du joueur pour vérifier que le nombre augmente de 1 à chaque fois que tu collectes une étoile :

![Inspector montrant la variable étoiles définie sur 3 en mode Play.](images/stars-inspector.png)


**Debogage :** Si tu ne vois pas la variable `étoiles` dans Inspector, assure-toi d'avoir enregistré ton script `JoueurEtoile.cs`.

--- /task ---

Pouvoir voir combien d'étoiles ont été collectées est idéal pour tes tests, mais les utilisateurs ne pourront pas le voir.

<p style="border-left: solid; border-width:10px; border-color: #0faeb0; background-color: aliceblue; padding: 10px;">
<span style="color: #0faeb0">**UI**</span> ou éléments User Interface permettent à un projet Unity d'utiliser des objets tels que du texte, des boutons ou des curseurs pour communiquer et interagir avec l'utilisateur ou le joueur. Les éléments de l'UI sont souvent utilisés pour les écrans de démarrage et les paramètres du jeu, ainsi que pour donner des informations à l'utilisateur et lui permettre de faire des choix. 
</p>

--- task ---

Fais un clic droit dans la fenêtre Hierarchy et va à **UI** puis sélectionne **Text - TextMeshPro**. Cela crée un canevas avec un objet texte enfant ; tu peux voir le texte dans la vue **Game** :

![La vue Game avec "New Text" écrit sur l'écran.](images/new-text.png)

--- collapse ---

---
title: Première utilisation du message TextMeshPro
---

Tu verras peut-être une fenêtre contextuelle te demandant d'importer les éléments TextMeshPro essentials, examples, and extras dans ton projet. Si c'est le cas, clique successivement sur les deux boutons **Import**, puis ferme la fenêtre :

![La fenêtre contextuelle TMP Importer affichant deux composants supplémentaires de l'éditeur Unity à importer : TMP Essentials et TMP Examples and extras. Il y a deux boutons pour déclencher les importations.](images/TMP-importer.png)

--- /collapse ---

--- /task ---

--- task ---

Fais un clic droit sur le nouveau **Text - (TMP) GameObject** et sélectionne `rename`. Appelle-le `Texte Etoiles` pour l'identifier facilement :

![GameObject Etoiles renommé dans la fenêtre Hierachy.](images/stars-gameobject.png)

--- /task ---

--- task ---

Dans la fenêtre Inspector, pour le GameObject TextMeshPro, accède au composant **Text Input**. Modifie `New Text` en `Étoiles : 0` :

![La grande fenêtre de saisie de texte avec "Étoiles : 0" tapé.](images/stars-start-text.png)

--- /task ---

--- task ---

Dans le composant **Rect Transform**, clique et modifie l'alignement en **Top Left**. Et modifie la position en `x = 120`, `y = -50`.

Cela positionnera le centre de ton texte à 120 pixels de la gauche et à -50 pixels du haut. Le texte restera en place si tu redimensionnes la vue Game :

![La fenêtre Inspector avec le menu déroulant des préréglages d'ancrage affiché en haut à gauche et les valeurs "Pos x" et "Pos y" mises à jour.](images/reposition-text.png)


**Astuce :** Tu peux afficher la position du texte dans la vue Game même lorsque tu n'es pas en mode Play.

--- /task ---

Tu dois maintenant mettre à jour le texte affiché afin qu'il indique le nombre actuel d'étoiles collectées par le joueur.

--- task ---

Ouvre ton script `JoueurEtoile` et ajoute `using TMPro` en haut pour que ton script puisse utiliser `TMP_Text` :

--- code ---
---
language: cs filename: StarPlayer.cs line_numbers: true line_number_start: 1
line_highlights: 4
---
using System.Collections; using System.Collections.Generic; using UnityEngine; using TMPro; --- /code ---

--- /task ---

--- task ---

Ajoute du code pour créer un objet TMP_Text appelé `Texteetoile` :

--- code ---
---
language: python filename: StarPlayer.cs line_numbers: true line_number_start: 6
line_highlights: 9
---
public class StarPlayer : MonoBehaviour
{ public int stars = 0; // An integer whole number public TMP_Text starText; // Start is called before the first frame update --- /code ---

--- /task ---

--- task ---

Utilise la méthode `SetText` de la classe `TMP_Text` pour afficher le nombre d'étoiles collectées à chaque mise à jour :

--- code ---
---
language: python filename: StarPlayer.cs - Update() line_numbers: true line_number_start: 16
line_highlights: 21
---
public class StarPlayer : MonoBehaviour
{
    // Update is called once per frame
    void Update()
    {
        starText.SetText("Stars: " + stars);
    }
--- /code ---

Enregistre ton code et reviens à l'éditeur Unity.

--- /task ---

--- task ---

Dans la fenêtre Inspector du Player pour le script `JoueurEtoile`, clique sur le cercle à côté de la propriété Texte Etoile et choisis **Texte Etoile** pour lier ton objet texte.

![Stars Text sélectionné dans la fenêtre Inspector pour le Player.](images/stars_text.png)

--- /task ---

--- task ---

Joue ta scène et vérifie que le nombre dans le texte de l'interface utilisateur augmente à chaque fois que tu récupères une étoile :

![Le gif animé de la vue Game montre que le texte "Score : 2" devient "Score : 3" lorsqu'une autre étoile est collectée.](images/counting-stars.gif)

--- /task ---

--- save ---

