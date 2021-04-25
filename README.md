# <B>Impossible Creatures</B>

# Endpoints :<br>

• Méthode GET :<br>

- Liste des utilisateurs : <br>
URI : <i>http://127.0.0.1:8000/api/users</i><br>
Paramètres : /<br>
Réponse : Tous les utilisateurs et leurs informations sont listés.<br>

- Un utilisateur :<br>
URI : <i>http://127.0.0.1:8000/api/users/{id}</i><br>
Paramètres : {id} -> L'id de l'utilisateur recherché.<br>
Réponse : L'utilisateur et ses informations sont listés s'il existe avec un code 200. Sinon un code 400 est renvoyé.<br>

- Liste des espèces : <br>
URI : <i>http://127.0.0.1:8000/api/species</i><br>
Paramètres : /<br>
Réponse : Tous les espèces et leurs informations sont listés.<br>

- Une espèce :<br>
URI : <i>http://127.0.0.1:8000/api/species/{id}</i><br>
Paramètres : {id} -> L'id de l'espèce recherchée.<br>
Réponse : L'espèce et ses informations sont listés si elle existe avec un code 200. Sinon un code 400 est renvoyé.<br>

- Liste des animaux : <br>
URI : <i>http://127.0.0.1:8000/api/animals</i><br>
Paramètres : /<br>
Réponse : Tous les utilisateurs et leurs informations sont listés.<br>

- Un animal :<br>
URI : <i>http://127.0.0.1:8000/api/animals/{id}</i><br>
Paramètres : {id} -> L'id de l'animal recherché.<br>
Réponse : L'animal et ses informations sont listés s'il existe avec un code 200. Sinon un code 400 est renvoyé.<br><br>

- Liste tous les animaux que possède un utilisateur : <br>
URI : <i>http://127.0.0.1:8000/api/user_has_animals/{id]</i><br>
Paramètres : {id} -> L'id de l'utilisateur recherché<br>
Réponse : Les animaux que possède l'utilisateur sont renvoyés avec un code 200. Sinon un code 400 est renvoyé.<br>

- Liste des espèces créées par un utilisateur : <br>
URI : <i>http://127.0.0.1:8000/api/user_has_species/{id}</i><br>
Paramètres : {id} -> L'id de l'utilisateur recherché<br>
Réponse : Les espèces créées par l'utilisateur sont renvoyés avec un code 200. Sinon un code 400 est renvoyé.<br>

• Méthode POST :<br>

- S'inscire / créer un utilisateur : <br>
URI : <i>http://127.0.0.1:8000/api/register</i><br>
Paramètres : Un code JSON de la forme : <br>
<i>{<br>
    "username": "NewUser",<br>
    "password": "123",<br>
    "money": 0,<br>
    "points": 0,<br>
    "animals": "les animaux",<br>
    "species": "les espèces"<br>
}</i><br>
Réponse : Un nouvel utilisateur est créé dans la base de données avec un code 201. Sinon un code 400 est renvoyé.<br>

- S'inscire / Créer un utilisateur : <br>
URI : <i>http://127.0.0.1:8000/api/register</i><br>
Paramètres : Un code JSON de la forme : <br>
<i>{<br>
    "username": "NewUser",<br>
    "password": "123"<br>
}</i><br>
Réponse : Si l'utilisateur existe et que le mot de passe est correct, un code 200 est renvoyé. Sinon c'est un code 400.<br>

- Créer une nouvelle espèce : <br>
URI : <i>http://127.0.0.1:8000/api/species</i><br>
Paramètres : Un code JSON de la forme : <br>
<i>{<br>
    "name": "NewSpecie",<br>
    "parent1": "parent",<B>*</B><br>
    "parent2": "other_parent",<B>*</B><br>
    "inventor": "1"<br>
}</i><br>
Réponse : Une nouvelle espèce est créée dans la base de données avec un code 201. Sinon un code 400 est renvoyé.<br>

- Créer un nouvel animal : <br>
URI : <i>http://127.0.0.1:8000/api/animals</i><br>
Paramètres : Un code JSON de la forme : <br>
<i>{<br>
    "name": "NewAnimal",<br>
    "species": "1",<br>
    "inventor": "1",<br>
    "owner": "1"<br>
}</i><br>
Réponse : Un nouvel animal est créé dans la base de données avec un code 201. Sinon un code 400 est renvoyé.<br><br>

• Méthode PUT :<br>

- Modifier un utilisateur : <br>
URI : <i>http://127.0.0.1:8000/api/users/{id}</i><br>
Paramètres : {id} -> L'id de l'utilisateur à modifier + Un code JSON de la forme : <br>
<i>{<br>
    "username": "NewValue",<br>
    "password": "NewValue",<br>
    "money": NewValue,<br>
    "points": NewValue,<br>
    "animals": "NewValue",<br>
    "species": "NewValue"<br>
 }</i><br>
Réponse : Si l'utilisateur existe, il est modifié avec les nouvelles valeurs et un code 200 est renvoyé. Sinon c'est un code 400.<br>

- Modifier une espèce : <br>
URI : <i>http://127.0.0.1:8000/api/species/{id}</i><br>
Paramètres : {id} -> L'id de l'espèce à modifier + Un code JSON de la forme : <br>
<i>{<br>
    "name": "NewValue",<br>
    "parent1": "NewValue",<br>
    "parent2": "NewValue",<br>
    "inventor": "NewValue"<br>
}</i><br>
Réponse : Si l'espèce existe, elle est modifiée avec les nouvelles valeurs et un code 200 est renvoyé. Sinon c'est un code 400.<br>

- Modifier un animal : <br>
URI : <i>http://127.0.0.1:8000/api/animals/{id}</i><br>
Paramètres : {id} -> L'id de l'animal à modifier + Un code JSON de la forme : <br>
<i>{<br>
    "name": "NewValue",<br>
    "species": "NewValue",<br>
    "inventor": "NewValue?",<br>
    "owner": "NewValue"<br>
}</i><br>
Réponse : Si l'animal existe, il est modifié avec les nouvelles valeurs et un code 200 est renvoyé. Sinon c'est un code 400.<br><br>

• Méthode DELETE :<br>

- Supprimer un utilisateur : <br>
URI : <i>http://127.0.0.1:8000/api/users/{id}</i><br>
Paramètres : {id} -> L'id de l'utilisateur recherché.<br>
Réponse : L'utilisateur et ses informations sont supprimés s'il existe avec un code 200. Sinon un code 400 est renvoyé.<br>

- Supprimer une espèce : <br>
URI : <i>http://127.0.0.1:8000/api/species/{id}</i><br>
Paramètres : {id} -> L'id de l'espèce recherchée.<br>
Réponse : L'animal et ses informations sont supprimés s'il existe avec un code 200. Sinon un code 400 est renvoyé.<br>

- Supprimer un animal : <br>
URI : <i>http://127.0.0.1:8000/api/animals/{id}</i><br>
Paramètres : {id} -> L'id de l'animal recherché.<br>
Réponse : L'espèce et ses informations sont supprimés si elle existe avec un code 200. Sinon un code 400 est renvoyé.<br>