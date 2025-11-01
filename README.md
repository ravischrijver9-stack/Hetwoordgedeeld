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
            font-size: 1.8rem;
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
            overflow-y: auto;
        }

        .content h2 {
            color: #243575;
            margin-top: 0;
        }

        .content p, .content ul, .content li {
            line-height: 1.6;
            margin-bottom: 1rem;
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
                Klik op een geloofsrichting om meer te lezen over de geschiedenis, overtuigingen en verhalen.
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
Ze ontstond in de vroege eeuwen van het christendom, met de paus in Rome als geestelijk leider. 
De katholieke traditie benadrukt zowel geloof als goede werken, en ziet de kerk als de gemeenschap 
waarin Gods genade zichtbaar wordt.</p>

<p>Centraal staan de zeven sacramenten: doopsel, vormsel, eucharistie, biecht, huwelijk, priesterwijding en ziekenzalving. 
Deze rituelen zijn momenten waarop de gelovige op een bijzondere manier Gods nabijheid ervaart.</p>

<h3>Belangrijke Bijbelverhalen:</h3>
<ul>
<li><strong>De schepping:</strong> God schept de wereld in zes dagen en rust op de zevende dag. Dit verhaal laat zien hoe God orde en schoonheid bracht in de chaos.</li>
<li><strong>Noach en de ark:</strong> Noach bouwt een ark om mens en dier te redden van de zondvloed. Vertrouwen en gehoorzaamheid aan God staan centraal.</li>
<li><strong>De Exodus:</strong> Mozes leidt het volk Israël uit Egypte en ontvangt de Tien Geboden. Dit laat Gods leiding en beloften zien.</li>
<li><strong>Jezus’ leven:</strong> Jezus geneest zieken, leert bidden en predikt liefde voor de naaste. Zijn kruisiging en opstanding vormen het hart van het christelijk geloof.</li>
<li><strong>Parabel van de verloren zoon:</strong> Een verhaal over vergeving en liefde van God.</li>
</ul>

<p>De katholieke kerk heeft een rijke kunst- en muziekgeschiedenis. Bedevaarten naar plaatsen zoals Lourdes of Rome zijn voor katholieken momenten van bezinning. De kerk stimuleert maatschappelijke zorg via scholen, ziekenhuizen en armenzorg.</p>
`,

            protestant: `
<h2>Protestantisme</h2>
<p>Het protestantisme ontstond in de 16e eeuw als hervormingsbeweging binnen het christendom. Hervormers zoals Maarten Luther en Johannes Calvijn wilden terug naar de kern van het geloof: de Bijbel als enige bron van gezag en Gods genade als weg tot verlossing.</p>

<h3>Belangrijke Bijbelverhalen:</h3>
<ul>
<li><strong>Het verhaal van David en Goliath:</strong> David vertrouwt op God om de reus Goliath te verslaan. Vertrouwen op God is belangrijker dan kracht.</li>
<li><strong>De Bergrede:</strong> Jezus leert over barmhartigheid, liefde en nederigheid. Dit legt de basis van het protestantse ethische leven.</li>
<li><strong>De vrucht van de Geest:</strong> Liefde, vreugde, vrede, geduld, vriendelijkheid, goedheid, trouw, zachtmoedigheid en zelfbeheersing als kenmerken van een christelijk leven.</li>
</ul>

<p>Protestanten geloven dat ieder mens een directe relatie met God kan hebben zonder tussenkomst van priesters. Het persoonlijke geloof en Bijbellezen staan centraal, evenals gebed en het toepassen van Gods wil in het dagelijks leven.</p>
`,

            orthodox: `
<h2>Oosters-Orthodoxie</h2>
<p>De Oosters-Orthodoxe Kerk is een van de oudste christelijke tradities ter wereld. Ze ontstond in het oostelijke deel van het Romeinse Rijk, met centra zoals Constantinopel en Jeruzalem.</p>

<h3>Belangrijke Bijbelverhalen:</h3>
<ul>
<li><strong>De schepping en Adam en Eva:</strong> De oorsprong van de mens en de zondeval.</li>
<li><strong>Moses en de Tien Geboden:</strong> De wet van God als richtlijn voor een heilig leven.</li>
<li><strong>Jezus’ wonderen:</strong> Genezing van zieken, water in wijn veranderen en opstanding van Lazarus.</li>
</ul>

<p>De orthodoxe eredienst is rijk aan symboliek, iconen en gezangen. Iconen worden gezien als vensters naar het goddelijke en spelen een centrale rol. Het uiteindelijke doel is 'theosis', één worden met God door gebed en nederigheid.</p>
`,

            islam: `
<h2>Islam</h2>
<p>De islam is een van de grote wereldreligies en werd in de 7e eeuw gesticht door de profeet Mohammed in Arabië. Moslims geloven in één God — Allah — en zien Mohammed als de laatste profeet.</p>

<h3>Belangrijke verhalen:</h3>
<ul>
<li><strong>De openbaringen aan Mohammed:</strong> De Koran bevat richtlijnen voor geloof, gebed en dagelijks leven.</li>
<li><strong>Abraham en Ismaël:</strong> Symbolen van trouw en gehoorzaamheid aan God.</li>
<li><strong>Moses en de profeten:</strong> Zij brengen de boodschap van één God naar hun volk.</li>
</ul>

<p>De vijf zuilen van de islam zijn: geloofsgetuigenis, gebed, aalmoezen, vasten in Ramadan en de hadj naar Mekka. Islam benadrukt gemeenschapszin, rechtvaardigheid en vrede.</p>
`,

            jodendom: `
<h2>Jodendom</h2>
<p>Het jodendom is een van de oudste monotheïstische religies. Het ontstond ruim drieduizend jaar geleden in Israël en vormt de basis van christendom en islam. Het joodse volk gelooft in één God die een verbond sloot met Abraham.</p>

<h3>Belangrijke verhalen:</h3>
<ul>
<li><strong>De Tora:</strong> Bevat de wetten en verhalen die het fundament van het joodse geloof vormen.</li>
<li><strong>De uittocht uit Egypte:</strong> Mozes leidt het volk Israël naar vrijheid, herinnert aan Gods bescherming en leiding.</li>
<li><strong>David en Salomo:</strong> Koningen die wijsheid en leiderschap tonen volgens Gods wil.</li>
</ul>

<p>Rituelen zoals sabbat, besnijdenis en feesten als Pesach en Chanoeka vormen de kern van het joodse leven. De synagoge is het centrum voor gebed en gemeenschap. Het jodendom legt nadruk op rechtvaardigheid, gemeenschap en hoop, ondanks de uitdagingen van de geschiedenis.</p>
`
        };

        function toonInhoud(onderwerp) {
            document.getElementById("content").innerHTML = teksten[onderwerp];
        }
    </script>
</body>
</html>
