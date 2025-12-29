<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<title>Mon site Commerces/Ventes</title>
<style>
    body {
        font-family: Arial, sans-serif;
        margin: 0;
        padding: 0;
        background: linear-gradient(#87CEEB, #e0f7fa);
        height: 100%;
        overflow-x: hidden;
        color: #000;
        transition: background 0.3s, color 0.3s;
    }

    header {
        background-color: #4CAF50;
        color: white;
        padding: 20px;
        text-align: center;
        transition: background-color 0.3s, color 0.3s;
    }

    main {
        padding: 20px;
        margin-bottom: 60px;
    }

    footer {
        background-color: #333;
        color: black;
        text-align: center;
        padding: 10px;
        position: fixed;
        bottom: 0;
        width: 100%;
        transition: background-color 0.3s, color 0.3s;
    }

    /* Onglets */
    .tabs {
        display: flex;
        flex-wrap: wrap;
        border-bottom: 2px solid #ccc;
        margin-bottom: 20px;
        transition: border-color 0.3s;
    }

    .tab {
        padding: 10px 20px;
        cursor: pointer;
        border: none;
        background: none;
        font-size: 16px;
        color: #000;
        transition: color 0.3s;
    }

    .tab.active {
        border-bottom: 3px solid #4CAF50;
        font-weight: bold;
    }

    .content {
        display: none;
        margin-top: 20px;
        color: inherit;
        transition: color 0.3s;
    }

    .content.active {
        display: block;
    }

    /* Grille responsive pour Ventes */
    #grilleVentes {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
        gap: 15px;
    }

    .blocCarre {
        width: 100%;
        aspect-ratio: 1/1; /* Toujours carré */
        border: 2px dashed #4CAF50;
        border-radius: 10px;
        background-color: #f9fff9;
        display: flex;
        justify-content: center;
        align-items: center;
        cursor: pointer;
        position: relative;
        overflow: hidden;
        transition: background-color 0.3s, border-color 0.3s;
    }

    .blocCarre img {
        width: 100%;
        height: 100%;
        object-fit: cover;
    }

    .blocCarre.dragover {
        background-color: #e0ffe0;
    }

    /* Boutons dans Infos */
    #btnConfidentialite, #btnCredit, #btnToggleMode {
        padding: 10px 15px;
        font-size: 16px;
        background-color: #4CAF50;
        color: white;
        border: none;
        border-radius: 5px;
        cursor: pointer;
        margin-top: 10px;
        display: inline-block;
        transition: background-color 0.3s, color 0.3s;
    }

    #texteConfidentialite, #texteCredit {
        display: none;
        margin-top: 10px;
        padding: 10px;
        border: 1px solid #4CAF50;
        border-radius: 5px;
        background-color: #f9fff9;
        color: #000;
        transition: background-color 0.3s, color 0.3s, border-color 0.3s;
    }

    /* Nuages */
    .nuage {
        position: absolute;
        background: white;
        border-radius: 50%;
        opacity: 0.8;
        transition: background 0.3s;
    }
    #nuage1 { width: 120px; height: 60px; top: 50px; left: -150px; }
    #nuage2 { width: 180px; height: 80px; top: 120px; left: -200px; }
    #nuage3 { width: 100px; height: 50px; top: 200px; left: -120px; }

    /* Oiseaux */
    .oiseau {
        position: absolute;
        font-size: 24px;
        transition: color 0.3s;
    }

    /* MODE SOMBRE */
    body.dark-mode {
        background: linear-gradient(#121212, #1c1c1c);
        color: #ddd;
    }

    body.dark-mode header {
        background-color: #222;
        color: #ddd;
    }

    body.dark-mode footer {
        background-color: #111;
        color: #ccc;
    }

    body.dark-mode .tabs {
        border-bottom-color: #555;
    }

    body.dark-mode .tab {
        color: #ccc;
    }

    body.dark-mode .tab.active {
        border-bottom-color: #90ee90;
        font-weight: bold;
    }

    body.dark-mode .content {
        color: #ddd;
    }

    body.dark-mode .blocCarre {
        background-color: #333;
        border-color: #90ee90;
    }

    body.dark-mode #btnConfidentialite,
    body.dark-mode #btnCredit,
    body.dark-mode #btnToggleMode {
        background-color: #90ee90;
        color: #111;
    }

    body.dark-mode #texteConfidentialite,
    body.dark-mode #texteCredit {
        background-color: #222;
        border-color: #90ee90;
        color: #ddd;
    }

    body.dark-mode .nuage {
        background: #bbb;
    }

    body.dark-mode .oiseau {
        color: #90ee90;
    }
</style>
</head>
<body>

<header>
    <h1>Bienvenue</h1>
    <p>Commerces/Ventes</p>
</header>

<main>
    <!-- Onglets -->
    <div class="tabs">
        <button class="tab active" onclick="openTab('accueil', event)">Accueil</button>
        <button class="tab" onclick="openTab('parametres', event)">Paramètres</button>
        <button class="tab" onclick="openTab('infos', event)">Infos</button>
        <button class="tab" onclick="openTab('ventes', event)">Ventes</button>
    </div>

    <!-- Contenu des onglets -->
    <div id="accueil" class="content active">
        <h2>Accueil</h2>
        <p>Bienvenue sur mon site 😄

🛡️ Gestion de la Sécurité (Anti-Scam)
Puisque les transactions se font en dehors de la plateforme (via SMS, WhatsApp, etc.), la modération aura un défi de taille.

Système de réputation : Permettre aux acheteurs de laisser une note sur le profil du vendeur après une discussion.

Signalement rapide : Un bouton "Signaler" bien visible sur chaque annonce ou profil.

Guide de prévention : Affiche un message d'avertissement conseillant aux utilisateurs de ne jamais payer avant d'avoir une preuve de l'envoi du contenu.

💬 L'Espace de Discussion
Pour faciliter les échanges sans que ce soit le chaos :

Filtrage automatique : Utiliser des outils pour bloquer les mots injurieux ou les liens suspects dès la zone de texte.

Notifications : Un système pour prévenir l'utilisateur qu'il a reçu une réponse sur le site afin qu'il n'oublie pas de venir vérifier.

📝 Organisation des Annonces
Le "brainrot" peut être très varié. Pour que les prix restent "abordables" et le site lisible :

Catégories : Vidéos, montages, scripts, mèmes personnalisés, etc.
</p>
    </div>

    <div id="parametres" class="content">
        <h2>Paramètres</h2>
        <p>Options et réglages du site.</p>
        <button id="btnToggleMode">Mode sombre / clair</button>
    </div>

    <div id="infos" class="content">
        <h2>Infos</h2>
        <p>Informations sur le site.</p>
        <button id="btnConfidentialite">Chartes et Confidentialité</button>
        <div id="texteConfidentialite">
            <h3>Charte et Confidentialité</h3>
            <p>Voici le texte de la charte et de la politique de confidentialité du site.</p>
        </div>

        <button id="btnCredit">Crédit</button>
        <div id="texteCredit">
            <h3>Crédit</h3>
            <p>Voici le texte des crédits du site.</p>
        </div>
    </div>

    <div id="ventes" class="content">
        <h2>Ventes</h2>
        <p>Ajouter des images des objets à vendre :</p>
        <div id="grilleVentes">
            <div class="blocCarre" data-index="0"></div>
            <div class="blocCarre" data-index="1"></div>
            <div class="blocCarre" data-index="2"></div>
            <div class="blocCarre" data-index="3"></div>
            <div class="blocCarre" data-index="4"></div>
            <div class="blocCarre" data-index="5"></div>
        </div>
        <input type="file" id="fichierInputCarre" accept="image/*" style="display:none;">
    </div>
</main>

<footer>
    © 2026 Mon site    
</footer>

<!-- Nuages et oiseaux -->
<div class="nuage" id="nuage1"></div>
<div class="nuage" id="nuage2"></div>
<div class="nuage" id="nuage3"></div>
<div class="oiseau" id="oiseau1">🐦</div>
<div class="oiseau" id="oiseau2">🐦</div>

<script>
    // Onglets
    function openTab(tabId, event) {
        document.querySelectorAll('.content').forEach(c => c.classList.remove('active'));
        document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
        document.getElementById(tabId).classList.add('active');
        event.target.classList.add('active');
    }

    // Boutons Infos (Chartes et Confidentialité + Crédit)
    const btnConf = document.getElementById('btnConfidentialite');
    const texteConf = document.getElementById('texteConfidentialite');
    btnConf.addEventListener('click', () => {
        texteConf.style.display = (texteConf.style.display === 'block') ? 'none' : 'block';
    });

    const btnCred = document.getElementById('btnCredit');
    const texteCred = document.getElementById('texteCredit');
    btnCred.addEventListener('click', () => {
        texteCred.style.display = (texteCred.style.display === 'block') ? 'none' : 'block';
    });

    // Bouton Mode sombre / clair
    const btnToggleMode = document.getElementById('btnToggleMode');
    btnToggleMode.addEventListener('click', () => {
        document.body.classList.toggle('dark-mode');
    });

    // Upload images carrés pour Ventes
    const blocs = document.querySelectorAll('.blocCarre');
    const inputCarre = document.getElementById('fichierInputCarre');

    blocs.forEach(bloc => {
        bloc.addEventListener('click', () => {
            inputCarre.dataset.bloc = bloc.dataset.index;
            inputCarre.click();
        });
        bloc.addEventListener('dragover', e => {
            e.preventDefault();
            bloc.classList.add('dragover');
        });
        bloc.addEventListener('dragleave', () => bloc.classList.remove('dragover'));
        bloc.addEventListener('drop', e => {
            e.preventDefault();
            bloc.classList.remove('dragover');
            const file = e.dataTransfer.files[0];
            if(file && file.type.startsWith('image/')) afficherImageBloc(bloc, file);
        });
    });

    inputCarre.addEventListener('change', () => {
        const index = inputCarre.dataset.bloc;
        const bloc = blocs[index];
        const file = inputCarre.files[0];
        if(file && file.type.startsWith('image/')) afficherImageBloc(bloc, file);
        inputCarre.value = '';
    });

    function afficherImageBloc(bloc, file) {
        const reader = new FileReader();
        reader.onload = e => {
            bloc.innerHTML = '';
            const img = document.createElement('img');
            img.src = e.target.result;

            const btn = document.createElement('button');
            btn.textContent = 'X';
            btn.style.position = 'absolute';
            btn.style.top = '2px';
            btn.style.right = '2px';
            btn.style.backgroundColor = 'red';
            btn.style.color = 'white';
            btn.style.border = 'none';
            btn.style.borderRadius = '3px';
            btn.style.cursor = 'pointer';
            btn.addEventListener('click', () => bloc.innerHTML = '');

            bloc.appendChild(img);
            bloc.appendChild(btn);
        }
        reader.readAsDataURL(file);
    }

    // Animation nuages
    const nuages = [
        {el: document.getElementById("nuage1"), speed: 0.3},
        {el: document.getElementById("nuage2"), speed: 0.2},
        {el: document.getElementById("nuage3"), speed: 0.25}
    ];
    function animeNuages() {
        nuages.forEach(n => {
            let left = parseFloat(n.el.style.left) || parseFloat(n.el.offsetLeft);
            left += n.speed;
            if(left > window.innerWidth + 100) left = -200;
            n.el.style.left = left + "px";
        });
        requestAnimationFrame(animeNuages);
    }
    animeNuages();

    // Animation oiseaux
    const oiseaux = [
        {el: document.getElementById("oiseau1"), x: 0, y: 50, dx: 1.5, dy: 0.5},
        {el: document.getElementById("oiseau2"), x: 0, y: 150, dx: 2, dy: -0.3}
    ];
    function animeOiseaux() {
        oiseaux.forEach(o => {
            o.x += o.dx;
            o.y += o.dy;
            if(o.x > window.innerWidth) o.x = -50;
            if(o.y > window.innerHeight) o.y = 0;
            if(o.y < 0) o.y = window.innerHeight;
            o.el.style.left = o.x + "px";
            o.el.style.top = o.y + "px";
        });
        requestAnimationFrame(animeOiseaux);
    }
    animeOiseaux();
</script>

</body>
</html>

<div id="ventes" class="content">
    <h2>Ventes</h2>
    <p>Ajouter des images des objets à vendre :</p>
    <div id="grilleVentes">
        <div class="blocCarre" data-index="0"></div>
        <div class="blocCarre" data-index="1"></div>
        <div class="blocCarre" data-index="2"></div>
        <div class="blocCarre" data-index="3"></div>
        <div class="blocCarre" data-index="4"></div>
        <div class="blocCarre" data-index="5"></div>
    </div>

    <h3>Images supplémentaires</h3>
    <div id="grilleSupplementaire" style="display: grid; grid-template-columns: repeat(auto-fill, minmax(150px, 1fr)); gap: 15px; margin-top: 20px;">
        <!-- 6 blocs supplémentaires -->
        <div class="blocCarreSup" data-index="0"></div>
        <div class="blocCarreSup" data-index="1"></div>
        <div class="blocCarreSup" data-index="2"></div>
        <div class="blocCarreSup" data-index="3"></div>
        <div class="blocCarreSup" data-index="4"></div>
        <div class="blocCarreSup" data-index="5"></div>
    </div>
    
    <!-- Input file caché pour les blocs principaux -->
    <input type="file" id="fichierInputCarre" accept="image/*" style="display:none;">
    <!-- Input file caché pour les blocs supplémentaires -->
    <input type="file" id="fichierInputSup" accept="image/*" style="display:none;">
</div>
