# Vanlige Git-kommandoer

Her er en oversikt over de mest brukte Git-kommandoene med korte beskrivelser på norsk.

## Oppsett

- `git config --global user.name "Ditt Navn"`
  - Angir brukernavnet som brukes i commit-historikken.
- `git config --global user.email "din@email.com"`
  - Angir e-postadressen som brukes i commit-historikken.
- `git config --global core.editor "kode --wait"`
  - Setter standard teksteditor for Git-meldinger.

## Arbeid med repositorier

- `git init`
  - Initialiserer et nytt Git-repositorium i gjeldende mappe.
- `git clone <url>`
  - Kopierer et eksternt repositorium til maskinen din.

## Filstatus og inspeksjon

- `git status`
  - Viser hvilke filer som er endret, lagt til eller klare for commit.
- `git diff`
  - Viser forskjeller mellom endringer i arbeidsområdet og staging-området.
- `git log`
  - Viser commit-historikken for repositoriet.
- `git log --oneline --graph --decorate --all`
  - Viser en kort og visuelt strukturert historikk.

## Legge til og commite endringer

- `git add <fil>`
  - Legger en fil til staging-området, klar for commit.
- `git add .`
  - Legger alle endrede filer i gjeldende mappe til staging.
- `git commit -m "melding"`
  - Lagrer endringene i repoet med en commit-melding.
- `git commit -am "melding"`
  - Legger til og commiter endrede sporbare filer i én kommando.

## Grener og branching

- `git branch`
  - Viser alle lokale grener i repositoriet.
- `git branch <navn>`
  - Oppretter en ny gren med navnet `<navn>`.
- `git checkout <gren>`
  - Bytter til en annen gren.
- `git checkout -b <navn>`
  - Oppretter og bytter til en ny gren.
- `git switch <gren>`
  - Bytter til en annen gren (moderne alternativ til checkout).
- `git switch -c <navn>`
  - Oppretter og bytter til en ny gren.

## Slå sammen og hente endringer

- `git merge <gren>`
  - Slår inn endringer fra `<gren>` til den gjeldende grenen.
- `git rebase <gren>`
  - Flytter og integrerer commits fra den gjeldende grenen over på `<gren>`.
- `git fetch`
  - Henter nye endringer fra fjernlageret uten å slå dem sammen.
- `git pull`
  - Henter og slår sammen endringer fra fjernlageret til gjeldende gren.
- `git push`
  - Sender lokale commits til fjernlageret.
- `git push -u origin <gren>`
  - Pusher en ny lokal gren til fjernlageret og setter upstream.

## Håndtering av endringer

- `git restore <fil>`
  - Gjenoppretter en fil fra siste commit til arbeidsområdet.
- `git restore --staged <fil>`
  - Fjerner en fil fra staging-området uten å endre arbeidskopien.
- `git reset --hard`
  - Tilbakestiller arbeidsområdet og staging til siste commit. Vær forsiktig.
- `git reset HEAD <fil>`
  - Fjerner en fil fra staging-området, men beholder endringene i arbeidskopien.

## Stash og midlertidig lagring

- `git stash`
  - Lagre midlertidig uferdige endringer for å rydde arbeidsområdet.
- `git stash apply`
  - Henter tilbake de lagrede endringene.
- `git stash pop`
  - Henter tilbake og fjerner stash-en.
- `git stash list`
  - Viser lagrede stashes.

## Fjernlager og samarbeid

- `git remote -v`
  - Viser fjernlagre som er koblet til repositoriet.
- `git remote add origin <url>`
  - Legger til et fjernlager med navnet `origin`.
- `git remote remove <navn>`
  - Fjerner en fjernlagerreferanse.
- `git fetch origin`
  - Henter data fra fjernlageret `origin`.

## Nyttige grep og inspeksjon

- `git show <commit>`
  - Viser detaljer og endringer for en commit.
- `git blame <fil>`
  - Viser hvem som endret hver linje i en fil og når.
- `git diff --staged`
  - Viser forskjeller for filer som er staged for commit.
- `git clean -n`
  - Viser hvilke filer som ville bli fjernet av `git clean`.
- `git clean -f`
  - Fjerner uversjonerte filer fra arbeidsområdet.

## Vanlige Git-arbeidsflyter

- `git checkout -b <gren>` / `git switch -c <gren>`
  - Opprett og bytt til en ny funksjonsgren før du begynner å jobbe.
- `git add .`
  - Legg til alle endringer når arbeidet er klart for commit.
- `git commit -m "Beskrivende melding"`
  - Lag en commit med en tydelig melding.
- `git pull --rebase`
  - Hent nye endringer fra fjernlager og integrer dem før du pusher.
- `git push`
  - Send ferdige commits til fjernlageret.
- `git fetch` + `git merge` eller `git rebase`
  - Bruk `fetch` først for å få oversikt, og velg `merge` eller `rebase` for å integrere endringene.
- `git stash` / `git stash pop`
  - Midlertidig lagre påbegynte endringer hvis du må bytte oppgave raskt.