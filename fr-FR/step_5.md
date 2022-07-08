## Conserver le temps

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
Maintenant qu'un joueur peut collecter des étoiles, ajoute un chronomètre pour indiquer le temps nécessaire pour collecter les trois étoiles. 
</div>
<div>
![La vue Game montrant une variable "étoiles" et une variable "temps" sur le canevas avec le chronomètre s'arrêtant lorsque la troisième étoile est collectée.](images/timer-stops.gif){:width="300px"}
</div>
</div>

<p style="border-left: solid; border-width:10px; border-color: #0faeb0; background-color: aliceblue; padding: 10px;">
<span style="color: #0faeb0">**Les mécanismes de jeu**</span> sont un élément clé de la conception d'un jeu. Ce sont les règles qui contrôlent les actions d'un joueur. Un **chronomètre** est un mécanisme de jeu qui ajoute un défi aux jeux vidéo. En fait, il existe de nombreux records du monde Guinness basés sur la rapidité avec laquelle les joueurs peuvent relever des défis dans les jeux !
</p>

Le joueur doit garder une trace du temps qu'il met pour terminer le mini-jeu, tu peux le faire avec une autre variable.

--- task ---

Dans la fenêtre Hierarchy, clique avec le bouton droit sur ton **Canvas** et à partir de UI, crée un autre **Text - TextMeshPro GameObject**. Tu verras "New text" écrit sur ton écran en vue Game :

![La vue Game avec un élément de texte de l'UI "New text" affiché sur l'écran.](images/new-timer.png)

--- /task ---

--- task ---

Fais un clic droit sur le nouveau **Text (TMP) GameObject** et sélectionne **rename**. Appelle-le `Time Text` pour l'identifier facilement :

![GameObject Time renommé dans la fenêtre Hierachy.](images/time-gameobject.png)

--- /task ---

--- task ---

Dans la fenêtre Inspector, dans la propriété Text Input du nouveau TextMeshPro GameObject, remplace `New Text` par `Time: 0`.

Utilise le composant **Rect Transform** pour changer l'alignement en **Top Right**. Modifie également la position en `x = -60`, `y = -50` :

![La fenêtre Inspector avec le menu déroulant Préréglages d'ancrage affiché en haut à droite et les valeurs "Pos x" = -60 et "Pos y" = - 50 mises à jour.](images/reposition-text-timer.png)

--- /task ---

Le texte affiché doit être mis à jour afin d'afficher en continu le nombre de secondes écoulées depuis le début du jeu.

--- task ---

Ouvre ton script `StarPlayer` et ajoute du code pour créer un objet TMP_Text appelé `timeText` :

--- code ---
---
language: cs
filename: StarPlayer.cs
line_numbers: true
line_number_start: 6
line_highlights: 10
---
public class StarPlayer : MonoBehaviour
{
    public int stars = 0; // Un nombre entier
    public TMP_Text starText;
    public TMP_Text timeText;
--- /code ---

--- /task ---

--- task ---

`Time.time` donne le temps en secondes depuis le démarrage de la scène. `Mathf.Round` transforme un nombre en un nombre entier.

Définis le texte pour afficher le nombre de secondes entières sur chaque mise à jour :

--- code ---
---
language: cs
filename: StarPlayer.cs - Update()
line_numbers: true
line_number_start: 18
line_highlights: 21
---
    void Update()
    {
        starText.SetText("Stars: " + stars);
        timeText.SetText("Time: " + Mathf.Round(Time.time));
    }
--- /code ---

Enregistre ton script et reviens à l'éditeur Unity.

--- /task ---

--- task ---

Sélectionne le joueur dans la fenêtre Hierarchy et accéde au composant de script `Star Player` dans la fenêtre Inspector. Clique sur le cercle à côté de `Time Text` et choisis ton nouvel objet "Time Text".

--- /task ---

--- task ---

**Test :** Exécute ton mini-jeu et vérifie que le temps se met à jour au fur et à mesure que tu joues. Que se passe-t-il lorsque tu collectes les trois étoiles ?

![Vue Game avec texte d'UI montrant trois étoiles collectées et un temps de 45 secondes.](images/both-texts-updating.gif)

--- /task ---

Le temps doit s'arrêter lorsque les trois étoiles sont collectées, mais actuellement, il continuera à compter tant que le mini-jeu se déroulera.

--- task ---

Ouvre le script `StarPlayer` et crée une instruction if autour de ton code temporel pour ne compter les secondes que si le joueur a collecté moins de trois étoiles :

--- code ---
---
language: python
filename: StarPlayer.cs - Update()
line_numbers: true
line_number_start: 18
line_highlights: 21-24
---
    void Update()
    {
        starText.SetText("Stars: " + stars);
        if (stars < 3)
        {
            timeText.SetText("Time: " + Mathf.Round(Time.time));
        }
    }
--- /code ---

Enregistre ton script et reviens à l'éditeur Unity.

--- /task ---

--- task ---

**Test :** Exécute à nouveau ton mini-jeu. Le chronomètre s'arrêtera lorsque le joueur aura trois étoiles :

![La vue Game montrant le chronomètre comptant à partir de 45 et s'arrêtant à 47 lorsque trois étoiles sont collectées.](images/timer-stops.gif)

--- /task ---

Après l'étape de réflexion, tu peux mettre à niveau ton projet avec les fonctionnalités que tu juges importantes.

--- save ---
