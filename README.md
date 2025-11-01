<!DOCTYPE html>
<html lang="nl">
<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width,initial-scale=1" />
    <title>Het Woord Gedeeld — waar je Verhalen uit bijbels kan lezen</title>
    <style>
        :root{
            --bg:#f6fafc;
            --card:#ffffff;
            --accent:#374151;
            --indigo:#2e3a8c;
            --muted:#6b7280;
            --highlight:#fde68a;
            --paper:#fbfdff;
            --border:#e6eef8;
            --green:#10b981;
        }
        *{box-sizing:border-box}
        body{
            margin:0;
            font-family: system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
            background:var(--bg);
            color:var(--accent);
            -webkit-font-smoothing:antialiased;
            -moz-osx-font-smoothing:grayscale;
            line-height:1.6;
        }
        header{
            background:linear-gradient(180deg, #233070 0%, #2e3a8c 100%);
            color:white;
            padding:1rem;
            position:sticky;
            top:0;
            z-index:30;
            box-shadow:0 6px 18px rgba(18,25,80,0.18);
        }
        .container{
            max-width:1100px;
            margin:1rem auto;
            padding:1rem;
        }
        .flex{display:flex}
        .gap-6{gap:1.5rem}
        .col{flex:1}
        .sidebar{
            width:280px;
            background:var(--card);
            border-radius:12px;
            padding:1rem;
            box-shadow:0 6px 20px rgba(32,40,80,0.06);
            border:1px solid var(--border);
            height:fit-content;
        }
        .brand{font-weight:700; font-size:1.4rem; letter-spacing:.2px}
        nav a{display:block; padding:.6rem .8rem; margin-bottom:.4rem; border-radius:8px; color:var(--accent); text-decoration:none; font-weight:600}
        nav a:hover{background:#eef6ff; color:var(--indigo)}
        .active{background:#e7f0ff; border-left:4px solid #3b82f6; color:var(--indigo)}
        main.card{
            background:var(--card);
            border-radius:12px;
            padding:1.25rem;
            box-shadow:0 6px 20px rgba(32,40,80,0.06);
            border:1px solid var(--border);
        }
        h1,h2,h3{margin:0 0 .6rem 0}
        h1{font-size:1.5rem}
        h2{font-size:1.25rem;color:var(--indigo)}
        h3{font-size:1.05rem;color:var(--accent)}
        .lead{color:var(--muted); margin-bottom:1rem}
        .section{margin-bottom:1.25rem; padding: .8rem; background:linear-gradient(180deg,#fbfdff, #fbfdff); border-radius:8px;}
        .subsection{margin-top:.5rem}
        .story-list{display:grid; gap:.6rem}
        .story-card{background:var(--paper); padding:.85rem; border-radius:8px; border:1px solid var(--border)}
        .story-card h4{margin:0 0 .4rem 0; font-size:1rem}
        .muted{color:var(--muted)}
        footer{padding:1rem; text-align:center; color:#fff; background:linear-gradient(180deg,#2e3a8c,#233070); margin-top:1rem}
        /* responsive */
        @media (max-width:900px){
            .flex{flex-direction:column}
            .sidebar{width:100%}
        }
        /* small helpers */
        .back{display:inline-block; margin-bottom:.8rem; color:var(--indigo); font-weight:600}
    </style>
</head>
<body>
    <header>
        <div class="container" style="display:flex; align-items:center; justify-content:space-between;">
            <div style="display:flex; align-items:center; gap:.75rem">
                <div class="brand">Het Woord Gedeeld</div>
                <div class="muted" style="font-weight:600; font-size:.95rem">— Bijbelverhalen & wereldreligies.</div>

        </div>
    </header>

    <div class="container flex gap-6">
        <aside class="sidebar" id="sidebar">
            <h2 style="margin-bottom:.6rem">Geloofsrichtingen</h2>
            <nav id="faith-navigation" aria-label="Geloofsrichtingen">
                <!-- wordt gevuld door JS -->
            </nav>
            <div style="margin-top:1rem; font-size:.9rem; color:var(--muted)">
                Tip: kies een geloof in de lijst om lange informatieve secties te lezen. Op mobiel verschijnen de secties onder elkaar.
            </div>
        </aside>

        <main class="card col" id="content-area" aria-live="polite">
            <!-- content wordt door JS geladen -->
            <h1>Welkom — Kies een geloof</h1>
            <p class="lead">Klik links op een geloofsrichting informatieve verhalen en thema’s te lezen. Elk onderwerp behandelt geschiedenis, kernleer, rituelen, belangrijke figuren, feesten en de moderne context.</p>
        </main>
    </div>

    <footer>
        &copy; 2025 Het Woord Gedeeld — Gemaakt door: Ravi Maas
    </footer>

    <script>
        // Uitgebreide, realistische teksten per geloof. Elke sectie bevat meerdere lange paragrafen.
        const faiths = {
            'katholiek': {
                id: 'katholiek',
                name: 'Rooms-Katholieke Kerk',
                overview: 'De Rooms-Katholieke Kerk is een wereldwijde christelijke traditie met diepe wortels in de vroege kerk. Haar theologie legt de nadruk op sacramenten, de apostolische traditie en de nauwe relatie tussen geloof en praktijk. Hieronder vind je historie, geloofsleer, sacramenten, belangrijke feesten en de moderne praktijk.',
                sections: [
                    {
                        title: 'Geschiedenis en ontwikkeling',
                        content: `De geschiedenis van de Katholieke Kerk begint bij de vroege christelijke gemeenschappen van de eerste eeuwen na Christus, waar apostelen en kerkelijke leiders doctrine en liturgie vormgaven in een mediterrane context. In de loop der eeuwen ontwikkelde de Kerk zich tot een uitgebreide organisatie met bisschoppen, theologische scholen en een gecodificeerde liturgie. De invloed van het Romeinse Rijk, de Middeleeuwse scholastiek en later hervormingen heeft de Kerk gevormd; belangrijke momenten zijn onder meer het Concilie van Nicea (325), de opkomst van kloosterorden in de Middeleeuwen en het conciliaire denken van het Tweede Vaticaans Concilie (1962–1965). De machtsstructuur van paus, bisschoppen en universiteiten hielp zowel de theologie als sociale instituties ontwikkelen—zoals ziekenzorg en onderwijs—waardoor de Kerk diepe maatschappelijke wortels kreeg.`
                    },
                    {
                        title: 'Kernleer en theologie',
                        content: `Centraal in de katholieke theologie staat de leer dat God zich volledig geopenbaard heeft in Jezus Christus, wiens leven, dood en opstanding het heil voor de mensheid mogelijk maken. De Kerk benadrukt zowel Schrift als Traditie als bronnen van openbaring; pausselijke en conciliaire besluiten worden gezien als behulpzaam bij het verstaan van de geloofsinhoud. De sacramenten (met name de Eucharistie) worden gezien als werkzame middelen van genade: in de Mis staat de herdenking van Christus’ offer centraal, waarbij de gelovige deelneemt aan het mysterie van verlossing. Ethiek in de Katholieke traditie combineert natuurlijke wet, de Schrift en pastorale overwegingen bij actuele vraagstukken.`
                    },
                    {
                        title: 'Sacramenten, rituelen en praktijk',
                        content: `De zeven sacramenten (doop, vormsel, eucharistie, boete/verzoening, huwelijk, priesterwijding en ziekenzalving) structureren het geestelijke leven van katholieken. Rituelen en sacramentele handelingen bieden momenten van persoonlijke en gemeenschappelijke overgang: geboorte, volwassen wording, huwelijk, ziekte en dood. De liturgie bevat psalmen, gebeden en symboliek die generaties lang zijn opgebouwd; voor velen is de weekelijkse Mis (eucharistieviering) het spirituele hart van hun geloof. Daarnaast spelen sacrale objecten, processies, devotie tot Maria en heiligen en vormen van pelgrimage (zoals Rome of Lourdes) een rol bij het beleven van geloof.`
                    },
                    {
                        title: 'Feesten en kalender',
                        content: `Het liturgische jaar organiseert het religieuze leven: Advent, Kerst, Vastentijd (lentetijd), Pasen en Pinksteren zijn de belangrijkste tijdstippen die het mysterie van Christus’ komst, lijden en opstanding markeren. Daarnaast zijn er feestdagen ter ere van Maria en talrijke heiligendagen die aandacht geven aan bepaalde figuren, gebeurtenissen of thema’s. Deze kalender vervult zowel theologische als pastorale functies: ze vormt de ritmiek van het jaar en draagt verhalen en waarden over aan gemeenschappen en gezinnen.`
                    },
                    {
                        title: 'Belangrijke figuren en invloed',
                        content: `Door de eeuwen heen zijn talloze theologen, mystici en leiders van grote invloed geweest: Augustinus van Hippo, Thomas van Aquino, Franciscus van Assisi en Teresa van Ávila zijn voorbeelden van denkers en spirituele vormen die diepe sporen nalieten. Pausen zoals Johannes Paulus II en paus Franciscus hebben in moderne tijden politieke, sociale en theologische thema's aangesneden — van mensenrechten tot ecologie. De sociale leer van de Kerk stimuleert arbeidsethiek, zorg voor armen en betrokkenheid bij rechtvaardigheidsvraagstukken.`
                    },
                    {
                        title: 'Moderne context en uitdagingen',
                        content: `De Katholieke Kerk staat in de moderne tijd voor vragen rond secularisatie, wetenschappelijke inzichten en de roep om vernieuwing binnen pastorale zorg. Schandalen, maatschappelijke polarisatie en de vraag naar rolverdeling (inclusief discussie over vrouwelijke diaconie en celibaat) hebben binnen en buiten de Kerk veel aandacht gekregen. Tegelijkertijd blijft de Kerk een belangrijke actor in onderwijs, gezondheidszorg en armoedebestrijding wereldwijd. In vele landen blijven parochies centra van sociale samenhang en gemeenschapsleven.`
                    }
                ]
            },

            'protestants': {
                id: 'protestants',
                name: 'Protestantisme',
                overview: 'Het protestantisme omvat veel verschillende denominations met gemeenschappelijke wortels in de Reformatie van de 16e eeuw. Thema’s zijn Schriftgezag, de centrale plaats van persoonlijke geloofsbeleving en vaak vereenvoudigde liturgische vormen.',
                sections: [
                    {
                        title: 'Oorsprong en Reformatie',
                        content: `Het protestantisme ontstond in de zestiende eeuw met figuren als Maarten Luther, Johannes Calvijn en anderen die kritiek leverden op praktijken en doctrines binnen de westerse kerk. De Reformatie benadrukte directe toegang tot de Bijbel, verwerping van bepaalde kerkelijke misstanden en de overtuiging dat verlossing alleen door geloof (sola fide) komt. Vanaf die periode splitsten zich verschillende stromingen af, elk met eigen accenten op predestinatie, sacramentologie en kerkelijke organisatie.`
                    },
                    {
                        title: 'Kernprincipes en geloofspraktijk',
                        content: `Belangrijke trekken van het protestantisme zijn de centrale plaats van de Schrift (sola scriptura), het nadruk op persoonlijke geloofservaring en de rol van prediking en gezang in de eredienst. Veel protestantse kerken erkennen twee sacramenten: doop en avondmaal, en benaderen deze vaak symbolischer dan in de katholieke traditie. Gemeentezeggenschap, catechese en studie van de Schrift zijn belangrijk; kerken organiseren geregelde verenigingen, huisgroepen en diaconale activiteiten.`
                    },
                    {
                        title: 'Diversiteit binnen het protestantisme',
                        content: `Binnen het protestantisme bestaan Lutheranen, Gereformeerden, Anglicanen, Baptisten, Methodisten en tal van vrije kerken. Elke traditie heeft eigen accenten: liturgische Orde bij sommige, evangelische nadruk op bekering en persoonlijke ontmoeting bij andere, en sociaal-ethische betrokkenheid weer bij andere stromingen. De variatie zorgt dat het protestantisme in cultuur en opvatting sterk uiteen kan lopen, van liturgisch en academisch tot charismatisch en missionair.`
                    },
                    {
                        title: 'Pastorale en maatschappelijke rol',
                        content: `Protestantse kerken hebben historisch bijgedragen aan alfabetisering, onderwijs en sociale projecten. In veel samenlevingen waren protestantse gemeenschappen actief in sociale vernieuwing en missionaire arbeid. In de moderne tijd ligt de nadruk vaak op integratie van geloof in dagelijks leven, zingeving en praktische hulpverlening. Kerkelijke organisaties werken samen met maatschappelijke instellingen en bijdragen aan dialoog en vrijheidsrechten.`
                    }
                ]
            },

            'oosters-orthodox': {
                id: 'oosters-orthodox',
                name: 'Oosters-Orthodoxie',
                overview: 'De Oosters-Orthodoxe traditie hecht veel waarde aan continuïteit met de vroege kerk, sacramentele leefwijze en de mystieke ervaring via gebed en iconen. Liturgie en traditie spelen een centrale rol.',
                sections: [
                    {
                        title: 'Historische wortels',
                        content: `De Oosters-Orthodoxe Kerk vindt haar wortels in de vroegchristelijke gemeenschappen van het oostelijke Middellandse Zeegebied. Na de christelijke oorsprong ontwikkelde de oosterse traditie zich in een culturele ruimte met Grieks, Slavische en andere invloeden. De breuk met de westerse kerk culmineerde in 1054 (het Groot Schisma), waarna Oosters-Orthodoxe kerken zich als autonome patriarchaten en lokale kerken organiseerden rondom Byzantijnse liturgische tradities.`
                    },
                    {
                        title: 'Liturgie, mystiek en iconen',
                        content: `De liturgie (vooral de Goddelijke Liturgie van Johannes Chrysostomus) is het centrum van eredienst; lange, symbolisch geladen gebeden en gezangen leiden de gelovige in deelname aan het hemelse mysterie. Iconen (heilige afbeeldingen) worden beschouwd als vensters naar het heilige: ze nodigen uit tot verering en innerlijke contemplatie, niet als objecten van aanbidding maar als middelen om te bidden en ontmoeting met heiligen te ervaren. Mystieke theologie, hesychasm (stille gebedspraktijken) en ascetische tradities zijn kenmerkend.`
                    },
                    {
                        title: 'Gemeenschap en pastorale structuur',
                        content: `Orthodoxe kerken zijn vaak georganiseerd in lokale bisdommen onder leiding van bisschoppen en patriarchen. De pastorale zorg combineert sacramentele dienstverlening met pastorale bezoeken en rituelen rond levensgebeurtenissen. Kerkelijke tradities en lokale gebruiken vormen samen een cultuur van samenkomen—feesten, processies en familievieringen versterken gemeenschapsbanden.`
                    },
                    {
                        title: 'Moderne uitdagingen en continuïteit',
                        content: `In de moderne tijd confronteren orthodoxe gemeenschappen zich met migratie, secularisatie en de nood om jongere generaties te bereiken. Tegelijk is de behoudende oriëntatie—het benadrukken van continuïteit en traditionele liturgie—een kracht waarmee identiteitsbehoud en spiritualiteit worden vormgegeven. Dialogen met andere christelijke kerken en wereldreligies vinden plaats, gericht op wederzijds begrip en samenwerking.`
                    }
                ]
            },

            'islam': {
                id: 'islam',
                name: 'Islam',
                overview: 'De Islam is een monotheïstische traditie die uitgaat van de openbaring aan de profeet Mohammed. Praktijk, ethiek en gemeenschapsleven draaien rond de vijf zuilen en de Koran als leidraad.',
                sections: [
                    {
                        title: 'Ontstaan en historische ontwikkeling',
                        content: `De Islam ontstond in de 7e eeuw in het Arabische schiereiland met de boodschap van Mohammed als profeet en boodschapper. De eerste openbaringen, vastgelegd in de Koran, en de praktijk (sunna) van Mohammed vormden de kern waaruit een snelle religieuze en politieke expansie volgde. Gedurende de daaropvolgende eeuwen ontwikkelden zich grote civiele en wetenschappelijke bloeiperioden onder islamitische heerschappijen, en ontstonden uiteenlopende schoolsystemen (madhhab) in jurisprudentie en theologie.`
                    },
                    {
                        title: 'Kernbegrippen en de Vijf Zuilen',
                        content: `Centraal staan de eenheid van God (tawhid), het geloof in profeten en het leven na de dood. De Vijf Zuilen — shahada (geloofsbelijdenis), salat (gebed), zakat (armezorg), sawm (vasten in de maand Ramadan) en hadj (bedevaart naar Mekka) — geven praktische structuur aan het religieuze leven. De Koran en de hadith (overleveringen van de profeet) vormen de basis voor geloofsbeleving en juridische interpretatie.`
                    },
                    {
                        title: 'Levenspraktijk, rituelen en recht',
                        content: `Islamitische praktijk omvat dagelijkse gebeden, reinigingsrituelen (wudu), rituele maaltijden en specifieke riten bij geboorte, huwelijk en overlijden. Juridische tradities (fiqh) behandelen persoonlijke status, handel, strafrecht en andere maatschappelijke kwesties; verschillende scholen leggen accenten anders, wat leidt tot veelvoudige lokale praxis. Religieuze leiders (imams, geleerden) bieden begeleiding bij interpretatie en gemeenschap.`
                    },
                    {
                        title: 'Feesten en sociale functies',
                        content: `Belangrijke feesten zijn Eid al-Fitr (viering aan het einde van de Ramadan) en Eid al-Adha (offerfeest). Deze momenten combineren gebed met synchrone sociale handelingen—het geven aan de armen, familiefeest en rituele handeling. In de moderne samenleving functioneren moskeeën als religieuze én sociale centra: onderwijs, liefdadigheid en politiek-maatschappelijke discussie vinden er plaats.`
                    },
                    {
                        title: 'Moderne dynamiek en diversiteit',
                        content: `De islamitische wereld is cultureel en theologisch divers: soennieten, sjiieten en kleinere stromingen verschillen in rituele en theologische invullingen. Moderne kwesties—zoals rechten van minderheden, rechtvaardigheid, genderverhoudingen en technologische verandering—worden binnen de islamitische traditie bediscussieerd met behulp van politieke, juridische en ethische bronnen. Tal van islamitische geleerden en gemeenschappen zoeken naar manieren om traditionele bronnen te integreren met hedendaagse omstandigheden.`
                    }
                ]
            },

            'jodendom': {
                id: 'jodendom',
                name: 'Jodendom',
                overview: 'Het Jodendom is een van de oudste monotheïstische religies, geworteld in het verbond tussen God en het volk Israël. Het leven wordt vormgegeven door de Torah, praktijken en gemeenschapstradities.',
                sections: [
                    {
                        title: 'Historie en het Verbond',
                        content: `Het verhaal van het Jodendom begint met aartsvaders zoals Abraham en wordt verder gevormd door gebeurtenissen als de uittocht uit Egypte en de Torah-openbaring aan Mozes. Het begrip van een verbond (bris) tussen God en het volk Israël vormt de morele en rituele kern: geboden (mitzvot) reguleren relatie met God en medemensen. Door de eeuwen heen hebben diaspora, koninkrijken, profeten en rabbinische traditie de religie en culturele identiteit gedefinieerd.`
                    },
                    {
                        title: 'De Torah en schriftelijke tradities',
                        content: `De Torah (de eerste vijf boeken) vormt de belangrijkste tekst; daarnaast zijn er schriftelijke en mondelinge tradities die in de Talmoed en later commentaar samengebracht zijn. Deze werken vormen het kader voor wetgeving, ethiek en rituelen. Joodse leer combineert juridische scherpzinnigheid met ethische reflecties en verhalen die gemeenschapsidentiteit en zingeving bieden.`
                    },
                    {
                        title: 'Rituelen, sabbat en feesten',
                        content: `De sabbat (Shabbat) is wekelijks ritueel: rust en samenkomen, gebed en maaltijd markeren een heilige tijd. Jaarfeesten als Pesach (uittocht en bevrijding), Jom Kipoer (Grote Verzoendag), Soekot (loofhuttenfeest), Chanoeka en Poerim dragen historische herinneringen en morele lessen over aan volgende generaties. Rituelen omvatten eten, gebed, voorlezen van teksten en symbolische handelingen die verbondenheid met verleden en gemeenschap verdiepen.`
                    },
                    {
                        title: 'Leiderschap en gemeenschapsleven',
                        content: `Het rabbinaat en synagogale structuur bieden leiding op liturgisch en juridisch gebied. Joodse vorming (zoals bar/bat mitswa) markeert volwassenwording en verantwoordelijke participatie in gebeds- en gemeenschapsleven. Door diaspora en moderne nationale staten zijn Joodse gemeenschappen wereldwijd verschillend georganiseerd, maar gedeelde tradities en teksten creëren blijvende verbondenheid.`
                    },
                    {
                        title: 'Hedendaagse kwesties en continuïteit',
                        content: `Joods leven in de moderne wereld combineert behoud van traditie met culturele creativiteit en openheid voor moderne wetenschap en maatschappelijk debat. Debatten over identiteit, secularisatie, pluraliteit en de relatie met andere gemeenschappen kenmerken de hedendaagse context. Tegelijkertijd blijven onderwijs, mutuele zorg en liturgische praktijk centraal staan in het voortbestaan van gemeenschappen.`
                    }
                ]
            }
        };

        // State
        let currentFaithId = null;

        // DOM refs
        const faithNav = document.getElementById('faith-navigation');
        const contentArea = document.getElementById('content-area');

        // Render sidebar navigation
        function renderSidebar(){
            faithNav.innerHTML = '';
            for(const key of Object.keys(faiths)){
                const f = faiths[key];
                const a = document.createElement('a');
                a.href = "#";
                a.textContent = f.name;
                a.dataset.id = f.id;
                if(f.id === currentFaithId) a.classList.add('active');
                a.addEventListener('click', (e)=>{
                    e.preventDefault();
                    currentFaithId = f.id;
                    renderSidebar();
                    renderContent();
                    window.scrollTo({top:0,behavior:'smooth'});
                });
                faithNav.appendChild(a);
            }
        }

        // Helper to create section HTML
        function createSectionHTML(title, text){
            return `<div class="section">
                        <h3>${escapeHtml(title)}</h3>
                        <div class="subsection"><p class="muted">${escapeHtml(text)}</p></div>
                    </div>`;
        }

        // Escape function to avoid accidental markup injection
        function escapeHtml(str){
            return String(str)
                .replace(/&/g, '&amp;')
                .replace(/</g, '&lt;')
                .replace(/>/g, '&gt;')
                .replace(/"/g, '&quot;')
                .replace(/'/g, '&#039;');
        }

        // Render main content
        function renderContent(){
            const id = currentFaithId;
            if(!id){
                contentArea.innerHTML = `<h1>Welkom — Kies een geloof</h1>
                <p class="lead">Klik links op een geloofsrichting om uitgebreide en informatieve verhalen en thema’s te lezen.</p>`;
                return;
            }
            const faith = faiths[id];
            if(!faith) return;

            let html = `<a href="#" class="back" id="back-button">← Terug naar overzicht</a>
                        <h1>${escapeHtml(faith.name)}</h1>
                        <p class="lead">${escapeHtml(faith.overview)}</p>`;

            for(const sec of faith.sections){
                html += createSectionHTML(sec.title, sec.content);
            }

            // Add an extra "verdieping" sectie met suggesties en bronnen (niet extern)
            html += `<div class="section">
                        <h3>Verdieping & praktische bronnen</h3>
                        <div class="subsection muted">
                            <p>Wil je meer weten? Lees religieuze teksten (zoals de Bijbel, Koran of Torah) in betrouwbare vertalingen en zoek moderne commentaren van erkende geleerden. Bezoek lokale bibliotheken of academische inleidingen voor historische context. Gesprekken met voorgangers en deelname aan kerkdiensten, synagogedrachts of moskeeactiviteiten (waar welkom) geven praktisch inzicht in hoe mensen deze tradities beleven.</p>
                            <p>Deze pagina biedt een overzichtelijk startpunt: elke sectie is bedoeld als samenvattende inleiding en als aanzet tot verdere, serieuze studie. Als je wilt kan ik per sectie nog meer verwijzingen en een leesplan maken.</p>
                        </div>
                    </div>`;

            contentArea.innerHTML = html;

            // back button handler
            const back = document.getElementById('back-button');
            if(back){
                back.addEventListener('click', (e)=>{
                    e.preventDefault();
                    currentFaithId = null;
                    renderSidebar();
                    renderContent();
                });
            }
        }

        // Init
        document.addEventListener('DOMContentLoaded', ()=>{
            renderSidebar();
            renderContent();
        });

    </script>
</body>
</html>
