import { useState } from "react";

export default function Home() { const [lang, setLang] = useState("hu");

const content = { hu: { title: "Üdvözöl a Magyar Mozi!", subtitle: "Streaming magyar filmek, sorozatok és TV csatornák világszerte – elérhető angol, magyar és több mint 15 más nyelven.", tv: "400+ magyar TV csatorna élőben", movies: "12 000+ film elérhető bármikor", series: "Több mint 3000 sorozat, magyarul és más nyelveken", pricing: "Havi előfizetés csak $28, 48 órás ingyenes próba!", faq: "Gyakran Ismételt Kérdések", contact: "Kapcsolat" }, en: { title: "Welcome to Magyar Mozi!", subtitle: "Stream Hungarian movies, series, and TV channels worldwide – available in English, Hungarian, and over 15 other languages.", tv: "400+ Hungarian live TV channels", movies: "12,000+ movies on demand", series: "More than 3,000 series in Hungarian and other languages", pricing: "Only $28/month, includes 48h free trial!", faq: "Frequently Asked Questions", contact: "Contact" }, cs: { title: "Vítejte na Magyar Mozi!", subtitle: "Streamujte maďarské filmy, seriály a televizní kanály po celém světě – dostupné v maďarštině a dalších 15+ jazycích.", tv: "400+ maďarských živých TV kanálů", movies: "Více než 12 000 filmů", series: "Přes 3 000 seriálů s dabingem", pricing: "Předplatné jen $28/měsíc včetně 48h zdarma", faq: "Často kladené otázky", contact: "Kontakt" } };

const current = content[lang];

return ( <div className="min-h-screen bg-cover bg-center text-white" style={{ backgroundImage: "url('/bg-cinema.jpg')" }}> <header className="bg-black bg-opacity-70 w-full p-4 flex flex-wrap justify-between items-center sticky top-0 z-50"> <h1 className="text-xl font-bold">Magyar Mozi</h1> <nav className="space-x-4 text-sm"> <button onClick={() => setLang("hu")}>HU</button> <button onClick={() => setLang("en")}>EN</button> <button onClick={() => setLang("cs")}>CS</button> <a href="#tv">TV</a> <a href="#movies">Filmek</a> <a href="#series">Sorozatok</a> <a href="#pricing">Árak</a> <a href="#faq">GYIK</a> <a href="#contact">{current.contact}</a> </nav> </header>

<main className="pt-28 text-center p-4 bg-black bg-opacity-60">
    <h2 className="text-4xl font-bold mb-4">{current.title}</h2>
    <p className="text-lg max-w-3xl mx-auto mb-6">{current.subtitle}</p>
    <a href="#pricing" className="bg-blue-600 hover:bg-blue-700 px-6 py-3 rounded text-white font-semibold">48 órás ingyenes próba</a>
  </main>

  <section id="tv" className="bg-black bg-opacity-80 p-10">
    <h3 className="text-2xl font-semibold mb-2">TV</h3>
    <p>{current.tv}</p>
  </section>

  <section id="movies" className="bg-black bg-opacity-80 p-10">
    <h3 className="text-2xl font-semibold mb-2">Filmek</h3>
    <p>{current.movies}</p>
  </section>

  <section id="series" className="bg-black bg-opacity-80 p-10">
    <h3 className="text-2xl font-semibold mb-2">Sorozatok</h3>
    <p>{current.series}</p>
  </section>

  <section id="pricing" className="bg-black bg-opacity-80 p-10">
    <h3 className="text-2xl font-semibold mb-2">{current.pricing}</h3>
    <a href="https://wa.me/14378300041" target="_blank" className="bg-green-600 px-6 py-2 mt-4 inline-block rounded hover:bg-green-700">Előfizetek WhatsApp-on</a>
  </section>

  <section id="faq" className="bg-black bg-opacity-80 p-10">
    <h3 className="text-2xl font-semibold mb-4">{current.faq}</h3>
    <details className="mb-2">
      <summary>Működik Kanadából / USA-ból?</summary>
      <p>Igen, a szolgáltatás világszerte működik (kivéve Magyarország).</p>
    </details>
    <details className="mb-2">
      <summary>Van ingyenes próba?</summary>
      <p>Igen, 48 órás teljes hozzáférés minden új felhasználónak.</p>
    </details>
    <details className="mb-2">
      <summary>Milyen eszközökön működik?</summary>
      <p>Telefon, tablet, PC, okos TV – minden modern eszköz támogatott.</p>
    </details>
  </section>

  <footer id="contact" className="bg-black bg-opacity-90 text-center p-6 text-sm">
    <p>{current.contact}: <a className="underline" href="https://facebook.com/MagyarMozhi" target="_blank">Facebook</a> | <a className="underline" href="https://wa.me/14378300041" target="_blank">WhatsApp</a></p>
    <p className="mt-2">&copy; 2025 Magyar Mozi. Minden jog fenntartva.</p>
  </footer>
</div>

); }


