# Codemas-2019
code game / advent czechitas

Otevřeme si v editoru soubor index.html. Včera jsme pracovali s částí <head></head> a upravili jsme si obsahu tagu <title></title>. V dalších dnes se budeme pohybovat hlavně v sekci <body></body>, kde bude uložená celá obsahová část naší hry. Na konci body by měl být tag <script src=“script.js“></script>. Pokud tam není, doplň si ho tam prosím. Propojí nám náš základní html soubor s JavaScriptem, kde bude celá logika hry.

Herní plocha

Celá naše hra poběží na canvasu. Je to super element, který se používá pro psaní 2D her a vykreslování různých obrázků pomocí JavaScriptu. Pokud už HTML trošku znáš, možná ti přijde divné, že obrázky nebudeme přidávat pomocí HTML a tagu <img>, ale pomocí JavaScriptu. Vše bude vysvětleno v následujících dnech, nemusíš se bát.

Do index.html nad tag <skript> umístíme tag <div></div>. To je značka, která nemá výchozí styl, ale označuje nám jakýsi oddíl na stránce. My do tohoto divu přidáme ještě jeden element, samotná canvas. Kód potom bude vypadat takto:

<div>
 <canvas></canvas>
</div>
Později se budeme potřebovat na tuto herní plochu odkazovat v JavaScriptu. K tomu je nutné, aby byl JavaScript schopen HTML prvek naší herní plochy ve stránce najít a vybrat. Jde to zařídit několika způsoby, ale ten nejjednodušší a nejbezpečnější je, když k prvku přidáme jednoznačný identifikátor, takzvané ID (čti jako aj-dý).

ID přidáváme jako tzv. HTML atribut do otevírací poloviny značky. Různých HTML atributů existuje spousta, ale mají vždy následující podobu: nazev="hodnota". Název atributu je v našem případě id, jako hodnotu si zvolíme vlastní název, např. "game".

Ke značce <div> přidáme:

<div id=“game“>
 <canvas></canvas>
</div>
A protože budeme chtít pracovat i s canvasem, tak přidáme ID i jemu, např. "canvas".

<div id=“game“>
 <canvas id=“canvas“></canvas>
</div>
V HTML jsme prozatím hotoví. Když si stránku zobrazíme (stiskneme tlačítko Run nad editorem), zjistíme, že se nic nezměnilo a stránka vypadá stále prázdná. Jak už jsme říkali, značka <div> sama o sobě nijak nevypadá, vzhled jí musíme nastavit my sami. Vzhled se nastavuje v CSS. Kliknutím v levém sloupci otevřeme soubor style.css.

Jak už jsme si dříve řekli, CSS je tzv. selektivní jazyk, nyní musíme vybrat z HTML elementy, které budeme chtít nastylovat. K tomu nám slouží ta ID, které jsme si do elementů napsali. Pojďme si upravit náš canvas. Zápis selektoru pro výběr canvasu vypadá takto:

#canvas {
}
Teď canvas upravíme. Potřebujeme mu přidat nějaký obrázek na pozadí. K tomu slouží vlastnost background-image, která má jako hodnotu funkci url(), kam do závorky uvedeme cestu k našemu obrázku. Aby bylo pozadí vždy přes celou plochu, nastavíme jeho velikost na 100 % velikosti ve vodorovném i svislém směru.

#canvas {
  background-image: url("obrazky/background.png");
  background-size: 100% 100%;
}
Pozadí je super, ale kolem máme bílou plochu na zbytku stránky a to se k naší hře moc nehodí. Nastavme si pozadí stránky na trochu příjemnější barvu. Barva pozadí se nastavuje vlastností background-color, jako hodnota se uvádí buď anglický název, nebo číselný kód barvy. My použijeme barvu #0e234d.

Zároveň pomocí vlastnosti color změníme i barvu písma na bílou (kód barvy #ffffff), abychom na tmavém pozadí viděli text, až ho později do naší hry přidáme. Pozadí a barvu textu pro celou stránku změníme tak, že je nastavíme značce <body>, která celou stránku v HTML obaluje.

Změnit bychom mohli i pozici celého canvasu, prozatím ho vidíme na levé straně. Mnohem lepší by bylo ho mít uprostřed. Celý canvas máme obalený tagem div s ID „game“. Pojďme tedy div pomocí vlastnosti text-align umístit na střed. Nastavme vlastnosti text-align hodnotu center. Po spuštění by canvas měl být umístěný na středu. Prozatím se nelekej toho, že je herní plocha tak malá. Její velikost nastavíme až zítra v JavaScriptu. Ukázkový kód najdeš zde.
