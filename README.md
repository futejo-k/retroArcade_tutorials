# České tutoriály pro Retro Arcade for Education
Kódy jsou psány tak jak jsou v blokové verzi

# Donkey Kong

## Krok 1: Vytvoření hráče
### on start:
- set mySprite to sprite ... of kind Player (přejmenovat mySprite na hráč nebo jak si chcete hráče pojmenovat, pozor na pojmenování player/Player, programu se to nebude líbit; vytvoření hráče)
- set hráč to position x:6 y:235 (možná změna podle vaší obrazovky a světa; přesune hráče na startovní pozici)
- move hráč with buttons vx:80 vy:0 (vx klidně i 100, ale vy vždy 0; vx znamená velocity x neboli rychlost posunu na horizontální ose, vy je velocity y neboli rychlost posunu na vertikální ose)
- set hráč ay to 500 (otestujte si, možná změna; ay znamená vertikální zrychlení, jak moc zrychlí hráč)
- camera follow sprite hráč (hráč bude středem pozornosti, hýbe se s ním kamera)

**Blok kódu po kroku 1:**

![on start po kroku 1](C:\Users\Caedis\Desktop\Retro_Arcade_Tutorials\DonkeyKong_img\OnStart_Krok1.png)

## Krok 2: Vytvoření světa
### on start:
- set background image to nothing (prázdná obrazovka, můžete si vybrat i obrázek)
- set background color to black (vyberte si vlastní barvu, originální donkey kong měl černé pozadí, pokud jste si vybrali jako pozadí obrázek, je tento krok zbytečný)
- set tilemap to ... (vytvořte si vlastní level, budete potřebovat blok platformy a blok žebříku, platformy musí být nastaveny jako zdi, žebřík ne)

**Blok kódu po kroku 2:**

![on start po kroku 2](C:\Users\Caedis\Desktop\Retro_Arcade_Tutorials\DonkeyKong_img\OnStart_Krok2.png)

## Krok 3: Pohyb hráče
### on left button pressed:
- set hráč image to ... (postava kouká doleva; možné animace)
### on right button pressed:
- set hráč image to ... (postava kouká doprava; možné animace)
### on down buton pressed:
- set hráč image to ... (postava se kouká dopředu a krčí se)
### on up button pressed:
```
if (is hráč hitting wall bottom)
{
	set hráč vy to -150; (nastaví vertikální rychlost na -150 abychom mohli skočit)
	if (is right button pressed)
	{
		set hráč image to ...; (skok vpravo, možná animace)
	}
	else if (is left button pressed)
	{
		set hráč image to ...; (skok vlevo, možná animace)
	}
}
```

**Bloky kódu po kroku 3:**

![on ... button po kroku 3](C:\Users\Caedis\Desktop\Retro_Arcade_Tutorials\DonkeyKong_img\OnButton_Krok3.png)

![on up button po kroku 3](C:\Users\Caedis\Desktop\Retro_Arcade_Tutorials\DonkeyKong_img\OnUpButton_Krok3.png)

## Krok 4: Žebřík
### on sprite of kind Player overlaps (obrázek žebříku) at location:
```
if (is up button pressed then)
{
	set hráč velocity to vx:0 vy:-50; (díky záporné vertikální rychlosti pojede náš hráč nahoru po žebříku)
	set hráč image to ...; (obrázek otočení zády, možná animace, pozor na šířku postavičky, musí být užší než mezera mezi dvěma platformami)
}
```


**Blok kódu po kroku 4:**

![on sprite po kroku 4](C:\Users\Caedis\Desktop\Retro_Arcade_Tutorials\DonkeyKong_img\OnSpriteOverlapsZebrik_Krok4.png)
