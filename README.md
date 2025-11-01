<html lang="nl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Het Woord Gedeeld</title>
    <style>
        body {
            margin: 0;
            font-family: "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
            background-color: #f8fafc;
            color: #222;
        }

        header {
            background-color: #243575;
            color: white;
            padding: 1.5rem 2rem;
        }

        header .brand {
            font-size: 1.6rem;
            font-weight: bold;
        }

        header .subtitle {
            font-size: 1rem;
            opacity: 0.8;
        }

        main {
            display: flex;
            flex-wrap: wrap;
            gap: 2rem;
            padding: 2rem;
            background-color: #273c90;
            color: white;
        }

        .sidebar, .content {
            background-color: #f8fafc;
            color: #333;
            border-radius: 15px;
            padding: 1.5rem;
            box-shadow: 0 4px 10px rgba(0,0,0,0.2);
        }

        .sidebar {
            flex: 1 1 280px;
            max-width: 350px;
        }

        .sidebar h2 {
            color: #273c90;
        }

        .sidebar ul {
            list-style: none;
            padding: 0;
        }

        .sidebar li {
            margin: .75rem 0;
            cursor: pointer;
            font-weight: 600;
            color: #243575;
            transition: color 0.2s;
        }

        .sidebar li:hover {
            color: #3c54d3;
        }

        .content {
            flex: 3 1 600px;
            min-height: 500px;
        }

        .content h2 {
            color: #243575;
            margin-top: 0;
        }

        footer {
            background-color: #243575;
            color: white;
            text-align: center;
            padding: 1rem;
            font-size: 0.95rem;
        }
    </style>
</head>
<body>
    <header>
        <div class="brand">Het Woord Gedeeld</div>
        <div class="subtitle">Bijbelverhalen en wereldreligies</div>
    </header>

    <main>
        <div class="sidebar">
            <h2>Geloofsrichtingen</h2>
            <ul>
                <li onclick="toonInhoud('katholiek')">Rooms-Katholieke Kerk</li>
                <li onclick="toonInhoud('protestant')">Protestantisme</li>
                <li onclick="toonInhoud('orthodox')">Oosters-Orthodoxie</li>
                <li onclick="toonInhoud('islam')">Islam</li>
                <li onclick="toonInhoud('jodendom')">Jodendom</li>
            </ul>
            <p style="font-size:0.9rem; color:#555; margin-top:1rem;">
                Klik op een geloofsrichting om meer te lezen over de geschiedenis, overtuigingen en tradities.
            </p>
        </div>

        <div class="content" id="content">
            <p>Klik links op een geloofsrichting om uitgebreide informatie te lezen.</p>
        </div>
    </main>

    <footer>
        © 2025 Het Woord Gedeeld — door Ravi Maas
    </footer>

    <script>
        const teksten = {
            katholiek: `
                <h2>Rooms-Katholieke Kerk</h2>
                <p>De Rooms-Katholieke Kerk is de grootste christelijke geloofsgemeenschap ter wereld. 
                Ze heeft haar oorsprong in de vroege eeuwen van het christendom, met de paus in Rome 
                als geestelijk leider. De katholieke traditie benadrukt zowel het geloof als de goede werken, 
                en ziet de kerk als de gemeenschap waarin Gods genade zichtbaar wordt.</p>
                
                <p>Centraal staan de zeven sacramenten: doopsel, vormsel, eucharistie, biecht, huwelijk, 
                priesterwijding en ziekenzalving. Deze rituelen zijn momenten waarop de gelovige op een bijzondere 
                manier Gods nabijheid ervaart. De eucharistieviering, of mis, is het hart van de katholieke eredienst 
                waarin de gelovigen samenkomen om het laatste avondmaal van Jezus te gedenken.</p>
                
                <p>De Rooms-Katholieke Kerk kent een rijke kunst- en gebedstraditie. Beelden, iconen en muziek 
                spelen een belangrijke rol in de beleving van het geloof. Bedevaarten, zoals naar Lourdes of Rome, 
                zijn voor veel katholieken momenten van bezinning en verbondenheid met de wereldkerk.</p>
            `,
            protestant: `
                <h2>Protestantisme</h2>
                <p>Het protestantisme ontstond in de zestiende eeuw als hervormingsbeweging binnen het christendom. 
                Hervormers als Maarten Luther en Johannes Calvijn wilden terug naar de kern van het geloof: 
                de Bijbel als enige bron van gezag en de genade van God als enige weg tot verlossing.</p>
                
                <p>Protestanten geloven dat ieder mens een directe relatie met God kan hebben, zonder tussenkomst van priesters. 
                De nadruk ligt op het persoonlijk lezen van de Bijbel, gebed en het leven naar Gods wil in het dagelijks bestaan. 
                In plaats van traditie en hiërarchie staat het individuele geloofsleven centraal.</p>
                
                <p>Er zijn vele protestantse stromingen, van luthersen tot gereformeerden, maar ze delen de overtuiging 
                dat geloof geen uiterlijk ritueel is, maar een innerlijke overtuiging die zich uit in daden van liefde 
                en gerechtigheid.</p>
            `,
            orthodox: `
                <h2>Oosters-Orthodoxie</h2>
                <p>De Oosters-Orthodoxe Kerk is een van de oudste christelijke tradities ter wereld. 
                Ze ontstond in het oostelijke deel van het Romeinse Rijk, met centra zoals Constantinopel, 
                Athene en Jeruzalem. De orthodoxe eredienst is rijk aan symboliek, zang en rituelen die 
                al eeuwenlang onveranderd zijn gebleven.</p>
                
                <p>Iconen spelen een belangrijke rol: ze worden niet als afbeeldingen, maar als vensters naar het goddelijke gezien. 
                Gelovigen kussen iconen als teken van eerbied en verbondenheid. De liturgie, vaak gezongen in het Kerkslavisch of Grieks, 
                wordt ervaren als een ontmoeting met de hemel op aarde.</p>
                
                <p>De orthodoxe theologie legt sterk de nadruk op de eenheid tussen mens en God. 
                Het uiteindelijke doel van het geloof is de 'theosis' — het steeds meer één worden met God door gebed, liefde en nederigheid.</p>
            `,
            islam: `
                <h2>Islam</h2>
                <p>De islam is een van de grote wereldreligies en werd in de zevende eeuw gesticht door de profeet Mohammed in Arabië. 
                Moslims geloven in één God — Allah — en zien Mohammed als de laatste profeet in een lange lijn van boodschappers, 
                waaronder Abraham, Mozes en Jezus.</p>
                
                <p>De Koran is het heilige boek van de islam. Het bevat openbaringen die Mohammed ontving en biedt richtlijnen 
                voor geloof, gebed, rechtvaardigheid en het dagelijks leven. Moslims volgen de vijf zuilen van de islam: 
                het geloofsgetuigenis, het gebed, het geven van aalmoezen, het vasten tijdens de maand Ramadan 
                en de bedevaart naar Mekka (de hadj).</p>
                
                <p>De islam kent vele culturen en tradities over de hele wereld, maar overal staan gastvrijheid, 
                rechtvaardigheid en gemeenschapszin centraal. Het geloof is niet alleen een overtuiging, 
                maar ook een manier van leven die gericht is op vrede en toewijding aan God.</p>
            `,
            jodendom: `
                <h2>Jodendom</h2>
                <p>Het jodendom is een van de oudste monotheïstische religies. Het ontstond ruim drieduizend jaar geleden 
                in het oude Israël en vormt de basis van zowel het christendom als de islam. 
                Het joodse volk gelooft in één God die een verbond sloot met Abraham en zijn nakomelingen.</p>
                
                <p>De Tora — de eerste vijf boeken van de Hebreeuwse Bijbel — bevat de wet en de verhalen die het fundament 
                van het joodse geloof vormen. Rituelen zoals de sabbat, de besnijdenis en de viering van feesten 
                zoals Pesach en Chanoeka spelen een belangrijke rol in het joodse leven.</p>
                
                <p>In het jodendom ligt veel nadruk op gemeenschap, rechtvaardigheid en het naleven van de geboden. 
                De synagoge is het centrum van gebed en samenkomst. Door de eeuwen heen is het jodendom 
                een geloof van hoop en volharding gebleven, dat zijn identiteit heeft behouden ondanks vervolging en diaspora.</p>
            `
        };

        function toonInhoud(onderwerp) {
            document.getElementById("content").innerHTML = teksten[onderwerp];
        }
    </script>
</body>
</html>
