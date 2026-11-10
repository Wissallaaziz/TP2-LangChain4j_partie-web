# Utilisation de l'intelligence artificielle – TP2 LangChain4j

## 1. Compilation et résolution des erreurs

### Problème rencontré
J'ai rencontré des difficultés pendant la compilation, notamment une erreur liée à un caractère BOM dans un fichier Java.

### Raison de l'utilisation de l'IA
Je ne parvenais pas à identifier l'origine de l'erreur et à la corriger seule dans un temps raisonnable.

### Prompt utilisé
J'ai transmis à l'IA le message d'erreur obtenu pendant l'exécution de Maven.

### Réponse de l'IA
L'IA m'a expliqué que le fichier contenait un caractère BOM au début et m'a proposé de réécrire le fichier en UTF-8 sans BOM avec PowerShell.

### Ce que j'ai appris
À reformuler avec mes propres mots après vérification : l'encodage d'un fichier peut provoquer des erreurs de compilation. UTF-8 sans BOM permet d'éviter l'ajout de certains caractères invisibles au début des fichiers Java.

## 2. Déploiement sur Payara et configuration de Gemini

### Problème rencontré
Après la compilation et le déploiement de l'application, j'ai rencontré une erreur HTTP 500 indiquant que GEMINI_KEY était absente. Après une modification de la configuration et un redémarrage de Payara, j'ai également rencontré une erreur HTTP 404.

### Raison de l'utilisation de l'IA
Je ne savais pas comment transmettre correctement la clé à Payara ni comment vérifier le déploiement de l'application.

### Prompt utilisé
« oui pourquoi ne pas deployer en utilisant une commande »

J'ai ensuite transmis les messages d'erreur HTTP 500 et HTTP 404 ainsi que les résultats des commandes PowerShell.

### Réponse de l'IA
L'IA m'a aidée à identifier une différence entre une variable d'environnement et une propriété JVM. Le code utilisait System.getProperty("GEMINI_KEY"). Elle m'a proposé d'ajouter la propriété JVM avec asadmin create-jvm-options, puis de redémarrer Payara. Elle m'a également guidée pour vérifier les applications déployées et leur contexte de déploiement.

### Ce que j'ai appris
une variable d'environnement et une propriété JVM sont deux mécanismes différents. Payara doit recevoir la propriété attendue par le code. La commande asadmin permet d'administrer Payara en ligne de commande, notamment pour déployer une application et consulter les applications déployées.