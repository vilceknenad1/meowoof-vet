# Meowoof veterinarska ordinacija

Statički sajt bez build koraka. Radi na GitHub Pages bez ikakvih dodatnih podešavanja.

## Objavljivanje na GitHub Pages

1. Napravite novi repozitorijum na GitHub-u, npr. `meowoof`. Može biti javan; GitHub Pages na besplatnom nalogu radi samo sa javnim repozitorijumima.
2. Otpakujte arhivu i otpremite **sadržaj** foldera, tako da `index.html` stoji u korenu repozitorijuma, ne u podfolderu.
   - Preko sajta: **Add file → Upload files**, prevucite sve fajlove i folder `img`.
   - Napomena: fajl `.nojekyll` je skriven. Na Mac-u ga prikažete sa `Cmd + Shift + .`, na Windows-u uključite „Hidden items”. Mora biti otpremljen.
3. U repozitorijumu otvorite **Settings → Pages**.
4. Pod **Source** izaberite **Deploy from a branch**, grana `main`, folder `/ (root)`, pa **Save**.
5. Posle 1–2 minuta sajt je na `https://VAŠE-IME.github.io/meowoof/`.

## Sopstveni domen (npr. veterinarzvezdara.com)

1. **Settings → Pages → Custom domain**: upišite domen i sačuvajte. GitHub sam pravi fajl `CNAME`.
2. Kod registra domena dodajte DNS zapise:
   - četiri `A` zapisa za `@`: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - `CNAME` zapis za `www` → `VAŠE-IME.github.io`
3. Kada DNS proradi (do 24h), uključite **Enforce HTTPS**.

`robots.txt` i `sitemap.xml` već pokazuju na `https://veterinarzvezdara.com/`. Ako koristite drugu adresu, promenite je u ta dva fajla.

## Forma za zakazivanje

GitHub Pages nema server, pa forma podrazumevano **otvara email program posetioca** sa popunjenom porukom ka `tatjana.dogdoorvet@gmail.com`.

Da bi upiti stizali direktno na email, bez otvaranja email programa:

1. U `index.html` pronađite red `const FORM_EMAIL = "";`
2. Upišite adresu: `const FORM_EMAIL = "tatjana.dogdoorvet@gmail.com";`
3. Otpremite izmenu i pošaljite jedan probni upit sa objavljenog sajta.
4. Na tu adresu stiže email od FormSubmit-a sa dugmetom za aktivaciju. Posle klika, svi upiti stižu direktno u inbox, kao tabela.

FormSubmit je besplatan i ne traži nalog. Forma ima zaštitu od spam botova (skriveno polje).

## Izmena sadržaja

Sav tekst usluga, radno vreme, recenzije i članci su na jednom mestu u `index.html`, u objektu `const CONTENT = {...}` pri dnu fajla.

- **Nova fotografija za uslugu:** stavite sliku u `img/` i kod te usluge promenite `img:null` u `img:"img/ime-slike.jpg"`.
- **Radno vreme:** `hours` (0 = nedelja, 6 = subota). Status „Sada radimo” na sajtu se računa automatski po beogradskom vremenu.
- Imena fajlova pišite **malim slovima, bez razmaka i bez naših slova**. GitHub razlikuje `Slika.jpg` i `slika.jpg`.

## Sadržaj foldera

| Fajl | Namena |
|---|---|
| `index.html` | ceo sajt |
| `404.html` | stranica za nepostojeće adrese |
| `img/` | fotografije, logo, favicon, slika za deljenje na mrežama |
| `.nojekyll` | isključuje Jekyll obradu na GitHub-u |
| `robots.txt`, `sitemap.xml` | za pretraživače |
