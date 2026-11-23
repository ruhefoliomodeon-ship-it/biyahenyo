# Karera ng Talino 3D

## Pag-install
1. I-extract ang ZIP.
2. Buksan ang folder sa Visual Studio Code.
3. I-install ang **Live Server** extension at pindutin ang **Go Live** sa `index.html`.
4. Kailangan ng internet para sa Three.js at Google Fonts (ang mga tanong ay lokal na naka-save).

## Files
- `index.html`: layout at navigation
- `style.css`: responsive UI
- `script.js`: Three.js scene, animation, rules, score, storage
- `questions.js`: editable bank ng mga tanong
- `build_bank.py`: optional Python script na ginamit upang likhain ang question bank; puwedeng baguhin at patakbuhin muli (kailangan ng Python 3)

## Mga tuntunin
- 8 tanong bawat round, isang kotse na umaabante ng isang checkpoint lamang pagkatapos ng tamang sagot.
- Unang subok na tama: 1 bituin. Unang subok na mali: 0 bituin sa checkpoint kahit mahanap ang tama sa mga susunod na subok.
- Hindi uulit ang eksaktong question ID sa kaparehong grade+subject selection hangga't hindi nauubos ang pool. Sa mixed modes, ang history ay hiwalay sa ibang modes.
- Ang history ay nasa `localStorage` ng browser, kaya nananatili matapos i-refresh sa parehong browser/origin. Maaari itong mabura kung i-clear ang browser storage o gumamit ng ibang browser.
- Ang 4,301 question entries ay kinabibilangan ng generated math problems at rephrased concept questions. **Hindi ito 4,301 magkakaibang konsepto.** Ang factual question bank ay paulit-ulit na core concepts na may ibang pananalita, at hindi pa isang opisyal na DepEd-aligned item bank. Ang grade level ng non-math items ay organizational filter lamang; i-review ang level bago gamitin sa klase.

## Pagdagdag ng tanong
Idagdag sa dulo ng `questions.js`:
```js
window.QUESTION_BANK.push({id:'custom_001',grade:4,subject:'science',question:'Ano ang tawag sa ating planeta?',choices:['Mars','Daigdig','Venus','Jupiter'],correct:1});
```
Ang `correct` ay 0-based index: 0=A, 1=B, 2=C, 3=D.

## Subjects
`math`, `filipino`, `english`, `science`, `ap`, `mapeh`, `values`.

## Nota
Procedural low-poly 3D ang world (hindi photorealistic), para magaan sa browser. Walang kinuhang copyrighted 3D assets. Ang `questions.js` ay malaki dahil naka-embed ang buong bank. Ang game ay walang server at walang user accounts.


## Sunny Kids Interface
Pumili ng grade at subject sa colorful card buttons (walang dropdown). Sa game screen, nasa kanang panel ang quiz sa desktop upang kitang-kita ang gumagalaw na 3D kotse sa kaliwa. Sa mobile, nakapatong ang quiz sa ibaba ng car scene.
