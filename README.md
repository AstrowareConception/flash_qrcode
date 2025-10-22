# Démo Scanner QR Code

Ce projet est une démonstration pédagogique d'un scanner de QR code pour appareils mobiles. Il a été conçu pour aider les étudiants à comprendre comment intégrer un système de scan de QR code dans leurs propres projets.
Pour tester sur votre téléphone : [https://astrowareconception.github.io/flash_qrcode/index.htm](https://astrowareconception.github.io/flash_qrcode/index.html) 

## Fonctionnalités

- Bouton "Flasher QRCode" qui active la caméra de l'appareil mobile
- Scan de QR code en temps réel
- Affichage du contenu du QR code après le scan
- Interface utilisateur simple et intuitive
- Explications détaillées du fonctionnement du code

## Comment utiliser cette démo

1. Ouvrez la page `index.html` sur votre appareil mobile (smartphone ou tablette)
2. Appuyez sur le bouton "Flasher QRCode"
3. Autorisez l'accès à la caméra si demandé
4. Pointez la caméra vers un QR code
5. Une fois le QR code détecté, la caméra se fermera automatiquement et le contenu du QR code s'affichera sur la page

## Prérequis techniques

- Un appareil mobile avec une caméra
- Un navigateur web moderne qui supporte l'API MediaDevices (Chrome, Firefox, Safari, Edge)
- Une connexion internet pour charger la bibliothèque html5-qrcode

## Comment ça marche

Cette démo utilise la bibliothèque [html5-qrcode](https://github.com/mebjas/html5-qrcode) qui permet de scanner des QR codes directement depuis le navigateur web sans avoir besoin d'installer d'application native.

Le code est organisé de la manière suivante:

1. **HTML**: Structure de base de la page avec les éléments UI nécessaires
2. **CSS**: Styles pour rendre l'interface utilisateur agréable et responsive
3. **JavaScript**: Logique pour initialiser le scanner, détecter les QR codes et afficher les résultats

## Intégration dans vos projets

Pour intégrer cette fonctionnalité dans vos propres projets:

1. Importez la bibliothèque html5-qrcode:
   ```html
   <script src="https://unpkg.com/html5-qrcode"></script>
   ```

2. Créez un conteneur pour le scanner:
   ```html
   <div id="qr-reader"></div>
   ```

3. Initialisez le scanner avec JavaScript:
   ```javascript
   const html5QrCode = new Html5Qrcode("qr-reader");
   html5QrCode.start(
       { facingMode: "environment" },
       { fps: 10, qrbox: 250 },
       (decodedText, decodedResult) => {
           // Gérer le résultat du scan ici
           console.log(`QR Code détecté: ${decodedText}`);
           html5QrCode.stop();
       },
       (error) => {
           // Gérer les erreurs ici
       }
   );
   ```

## Ressources supplémentaires

- [Documentation de html5-qrcode](https://github.com/mebjas/html5-qrcode)
- [MDN Web Docs: MediaDevices API](https://developer.mozilla.org/fr/docs/Web/API/MediaDevices)
- [Générateur de QR Code](https://www.qr-code-generator.com/) pour créer vos propres QR codes à tester

## Licence


Ce projet est disponible sous licence MIT. Vous êtes libre de l'utiliser, le modifier et le distribuer dans vos propres projets.
