# Labo Git & GitHub

## Doel van het labo

In dit labo heb ik geleerd hoe ik een lokale Git-repository kan koppelen aan GitHub en hoe ik wijzigingen tussen mijn lokale repository en GitHub kan synchroniseren.

## SSH

Ik heb een SSH-sleutelpaar aangemaakt en de publieke sleutel toegevoegd aan mijn GitHub-account.

De SSH-verbinding kan getest worden met:

```bash
ssh -T git@github.com
```

Hierdoor kan GitHub mijn computer authenticeren zonder dat ik telkens mijn wachtwoord moet ingeven.

## Git repository

Een lokale map kan een Git-repository worden met:

```bash
git init
```

Bestanden worden toegevoegd aan de staging area met:

```bash
git add .
```

Daarna kan een commit gemaakt worden:

```bash
git commit -m "Beschrijving van de wijziging"
```

Een commit bewaart de wijzigingen lokaal.

## GitHub koppelen

Een lokale repository kan gekoppeld worden aan een GitHub-repository met:

```bash
git remote add origin git@github.com:USERNAME/REPOSITORY.git
```

De remote kan gecontroleerd worden met:

```bash
git remote -v
```

## Push en pull

Met:

```bash
git push
```

worden lokale commits naar GitHub gestuurd.

Met:

```bash
git pull
```

worden wijzigingen van GitHub naar de lokale repository gehaald.

Belangrijk is dat een lokale commit niet automatisch op GitHub verschijnt. Daarvoor is een `git push` nodig.

Omgekeerd verschijnen wijzigingen die rechtstreeks via de GitHub-webinterface gemaakt worden niet automatisch lokaal. Daarvoor is een `git pull` nodig.

## Branch

Tijdens het labo heb ik de branch `master` hernoemd naar `main`:

```bash
git branch -M main
```

## Status controleren

Met:

```bash
git status
```

kan ik zien welke wijzigingen lokaal aanwezig zijn en of mijn lokale branch gesynchroniseerd is met GitHub.

## Merge conflict

Wanneer zowel lokaal als op GitHub dezelfde file wordt aangepast voordat de wijzigingen gesynchroniseerd zijn, kan een merge conflict ontstaan.

Een conflict kan opgelost worden met een merge tool, bijvoorbeeld Meld:

```bash
git mergetool
```

Daarna moet de opgeloste versie gecommit worden en kan ze naar GitHub gepusht worden.

## Belangrijkste commando's

| Commando              | Functie                             |
| --------------------- | ----------------------------------- |
| `git init`            | Nieuwe lokale Git-repository maken  |
| `git status`          | Status van de repository bekijken   |
| `git add .`           | Wijzigingen klaarzetten voor commit |
| `git commit -m "..."` | Wijzigingen lokaal opslaan          |
| `git push`            | Lokale commits naar GitHub sturen   |
| `git pull`            | Wijzigingen van GitHub ophalen      |
| `git remote -v`       | Gekoppelde remote bekijken          |
| `git branch`          | Branches bekijken                   |
| `git mergetool`       | Merge conflict oplossen             |

## Wat ik uit dit labo meeneem

Git houdt de geschiedenis van mijn project lokaal bij. GitHub is een remote repository waarmee ik mijn lokale repository kan synchroniseren. `commit` werkt lokaal, terwijl `push` en `pull` gebruikt worden om wijzigingen tussen mijn computer en GitHub uit te wisselen.
