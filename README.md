import React, { useState } from "react";

export default function DinnerPartyMenuSite() {
  const [selectedItems, setSelectedItems] = useState<string[]>([]);
  const [serviceStyle, setServiceStyle] = useState<"Buffet" | "Plated">("Buffet");

  const buffetItems = [
    // Existing buffet-style selections
    "Herb-Roasted Chicken with Lemon & Thyme",
    "Garlic Butter Salmon with Charred Lemon",
    "Slow-Braised Short Ribs",
    "Truffle Mashed Potatoes",
    "Roasted Seasonal Vegetables",
    "Garden Salad with House Vinaigrette",

    // From Dinner Party Menus (Menu 1 & 2)
    "Parmesan Crisp With Lemon Ricotta & Basil Oil",
    "Lemon–Saffron Risotto With Seared Scallop",
    "Prosciutto-Wrapped Asparagus With Truffle Hollandaise",
    "Herb-Crusted Lamb Rack With Rosemary Jus & Pommes Anna",
    "Honey-Lavender Panna Cotta With Raspberry Coulis",
    "Aji Amarillo Tartlet With Goat Cheese & Pickled Shallot",
    "Citrus-Cured Hamachi Crudo With Yuzu & Passionfruit",
    "Wild Mushroom & Corn Esquites Velouté",
    "Red Wine–Braised Short Rib With Mole Demi",
    "Dark Chocolate Torte With Mezcal Caramel",
  ];

  const platedItems = [
    // Existing plated dishes
    "Filet Mignon • Red Wine Jus • Potato Gratin",
    "Pan-Seared Sea Bass • Citrus Beurre Blanc • Asparagus",
    "Roasted Chicken Supreme • Herb Pan Sauce • Seasonal Vegetables",
    "Wild Mushroom Risotto • Parmesan • Truffle Oil",
    "Chocolate Lava Cake • Vanilla Bean Crème",

    // From NEW MENU SET #1
    "Smoked Salmon Rose • Dill Crème • Yuzu Pearl",
    "Truffled Cauliflower Velouté Shooter",
    "Beet-Cured Sea Bass Carpaccio • Passionfruit Vinaigrette",
    "White Asparagus Velouté • Crispy Jamón & Chive Oil",
    "King Oyster “Scallops” • Brown Butter • Lemon Ash",
    "Duck Confit Raviolo • Saffron Butter • Crispy Sage",
    "Roasted Duck Breast • Blackberry Gastrique • Parsnip Silk",
    "Charred Chilean Sea Bass • Aji Verde • Coconut Forbidden Rice",
    "Honeycomb Mousse Dome • Lemon Gel • Gold Leaf",
    "Burnt Basque Cheesecake • Guava Coulis",

    // From NEW MENU SET #2
    "Parmesan Custard • Anchovy Crisp • Basil Dust",
    "Patatas Bravas Bite • Paprika Aioli",
    "Charred Octopus Carpaccio • Smoked Paprika Oil • Citrus Ice",
    "Burrata Cloud • Tomato Water Gelée • Olive Soil",
    "Ricotta Gnocchetti • Pea Purée • Lemon Butter Foam",
    "Lobster Tortellini • Saffron Shell Broth",
    "Beef Tenderloin • Black Garlic Demi • Rosemary Polenta",
    "Seared Scallops • Romesco • Charred Fennel Pollen",
    "Olive Oil Citrus Cake • Rosemary Syrup • Mascarpone Silk",
    "Dark Chocolate Olive-Oil Crémeux • Sea Salt • Caramel Tuile",
  ];

  const activeItems = serviceStyle === "Buffet" ? buffetItems : platedItems;

  const toggleItem = (item: string) => {
    setSelectedItems((prev) =>
      prev.includes(item) ? prev.filter((i) => i !== item) : [...prev, item]
    );
  };

  return (
    <div className="min-h-screen bg-neutral-50 text-neutral-900 font-sans">
      {/* Header */}
      <header className="border-b bg-white/70 backdrop-blur sticky top-0 z-20">
        <div className="max-w-6xl mx-auto px-4 py-4 flex items-center justify-between">
          <div className="flex items-center gap-3">
            <div className="w-10 h-10 rounded-full border flex items-center justify-center text-xs tracking-[0.2em] uppercase">
              TP
            </div>
            <div>
              <p className="text-[0.65rem] uppercase tracking-[0.3em] text-neutral-500">
                Chef Paul — Private Chef Experience
              </p>
              <p className="font-semibold text-sm md:text-base">ChefPaul.co</p>
              <p className="text-xs italic text-neutral-500">
                Où chaque bouchée fait chavirer les sens
              </p>
            </div>
          </div>
        </div>
      </header>

      <main className="max-w-6xl mx-auto px-4 py-12 space-y-24">
        {/* HERO */}
        <section className="relative overflow-hidden rounded-3xl bg-neutral-900 text-neutral-50 p-12 shadow-xl">
          <div className="space-y-6 max-w-2xl">
            <p className="text-xs tracking-[0.35em] uppercase text-neutral-400">
              Chef Paul — Private Chef Experience
            </p>
            <h1 className="text-4xl md:text-5xl font-semibold leading-tight">
              Bespoke Dining Crafted Exclusively For You
            </h1>
            <p className="text-neutral-300 text-lg max-w-xl">
              A refined private-chef service offering immersive tasting menus,
              elegant plated dinners, and elevated buffet experiences — where
              every dish is curated with intention and artistry.
            </p>
          </div>
        </section>

        {/* ABOUT THE CHEF */}
        <section className="grid md:grid-cols-[minmax(0,260px)_1fr] gap-10 items-start">
          <div className="flex justify-center md:justify-start">
            <div className="relative w-52 h-52 rounded-3xl overflow-hidden shadow-xl border border-neutral-200 bg-neutral-100">
              <img
                src="/chef-paul-profile.jpg"
                alt="Chef Paul portrait"
                className="w-full h-full object-cover"
              />
            </div>
          </div>
          <div className="space-y-4">
            <h2 className="text-3xl font-semibold text-neutral-900">
              Meet Chef Paul
            </h2>
            <p className="text-neutral-700 text-sm uppercase tracking-[0.3em]">
              Where heritage, discipline & luxury dining meet
            </p>
            <div className="space-y-3 text-neutral-700 leading-relaxed text-sm md:text-base">
              <p>
                Where heritage, discipline, and luxury dining come together on a
                single plate. At Chef Paul – Private Chef Experience, every event
                becomes a curated journey inspired by my French and Caribbean
                roots, enriched by over 8 years of professional culinary
                experience, and refined through my education at the Culinary
                Institute of America (CIA) and the International Culinary Center
                (ICC) in New York.
              </p>
              <p>
                I&apos;ve honed my craft inside Michelin-recognized kitchens and
                some of the nation&apos;s most prestigious 5-star and Four-Diamond
                hotels and resorts, where precision, flavor, and flawless
                execution are the standard. These experiences shaped my
                commitment to excellence — from the ingredients I choose to the
                artistry behind every plate.
              </p>
              <p>
                My style blends the elegance of classical French technique with
                the vibrant, soulful flavors of the Caribbean, creating dishes
                that are refined, bold, and unforgettable. Whether you&apos;re
                hosting an intimate plated dinner, a luxurious multi-course
                tasting, or a beautifully curated buffet, each menu is designed
                exclusively for your event, crafted with high-end ingredients,
                expert technique, and Michelin-level presentation.
              </p>
              <p>
                From handcrafted amuse-bouches to signature entrées and
                show-stopping desserts, I oversee every detail — allowing you and
                your guests to relax, indulge, and savor a true fine-dining
                experience in the comfort of your home or venue.
              </p>
              <p>
                This isn&apos;t just dinner. It&apos;s culture. It&apos;s mastery.
                It&apos;s an experience — a celebration of flavor where French
                sophistication, Caribbean passion, and elite culinary training
                come together, one unforgettable bite at a time.
              </p>
            </div>
          </div>
        </section>

        {/* SERVICE + MENU BUILDER */}
        <section className="space-y-8">
          <h2 className="text-3xl font-semibold text-neutral-900">
            Customize Your Dining Experience
          </h2>
          <p className="text-neutral-600 max-w-xl">
            Select your preferred service style and tailor your menu from
            Chef Paul&apos;s curated culinary offerings.
          </p>

          {/* Toggle */}
          <div className="inline-flex rounded-full border bg-white p-1 text-sm shadow-sm">
            <button
              type="button"
              onClick={() => setServiceStyle("Buffet")}
              className={`px-6 py-2 rounded-full transition font-medium ${
                serviceStyle === "Buffet"
                  ? "bg-neutral-900 text-white"
                  : "text-neutral-700"
              }`}
            >
              Buffet Style
            </button>
            <button
              type="button"
              onClick={() => setServiceStyle("Plated")}
              className={`px-6 py-2 rounded-full transition font-medium ${
                serviceStyle === "Plated"
                  ? "bg-neutral-900 text-white"
                  : "text-neutral-700"
              }`}
            >
              Plated Dinner
            </button>
          </div>

          <div className="grid md:grid-cols-2 gap-10 items-start">
            {/* Available items */}
            <div className="bg-white rounded-3xl shadow-lg p-8 space-y-4 border border-neutral-200">
              <h3 className="text-2xl font-semibold">
                {serviceStyle === "Buffet"
                  ? "Buffet Menu Options"
                  : "Plated Course Options"}
              </h3>
              <p className="text-sm text-neutral-600">
                Select the dishes you&apos;d like featured in your experience.
              </p>
              <div className="space-y-3 max-h-[420px] overflow-y-auto pr-2">
                {activeItems.map((item) => (
                  <label
                    key={item}
                    className="flex items-center gap-3 cursor-pointer text-sm md:text-base"
                  >
                    <input
                      type="checkbox"
                      checked={selectedItems.includes(item)}
                      onChange={() => toggleItem(item)}
                      className="w-4 h-4 rounded border-neutral-400"
                    />
                    <span>{item}</span>
                  </label>
                ))}
              </div>
            </div>

            {/* Selected menu */}
            <div className="bg-neutral-900 text-neutral-50 rounded-3xl p-8 space-y-4 shadow-xl border border-neutral-800">
              <h3 className="text-2xl font-semibold">Your Custom Menu</h3>
              <p className="text-sm text-neutral-300">
                A refined summary of your selections — perfect for submitting
                your final dining request.
              </p>
              {selectedItems.length === 0 ? (
                <p className="text-sm text-neutral-400 italic">
                  No dishes selected yet. Begin by choosing items from the menu
                  options.
                </p>
              ) : (
                <ul className="list-disc pl-5 space-y-2 text-base">
                  {selectedItems.map((item) => (
                    <li key={item}>{item}</li>
                  ))}
                </ul>
              )}
            </div>
          </div>
        </section>

        {/* BOOKING CTA */}
        <section className="mt-20 bg-neutral-900 text-neutral-50 rounded-3xl p-12 shadow-xl border border-neutral-800 text-center space-y-6">
          <h2 className="text-3xl font-semibold">
            Book Your Private Dining Experience
          </h2>
          <p className="text-neutral-300 max-w-2xl mx-auto text-lg leading-relaxed">
            Reserve your date and allow Chef Paul to curate an unforgettable
            luxury dining experience crafted exclusively for you and your guests.
          </p>
          <a
            href="mailto:booking@chefpaul.co"
            className="inline-block mt-4 px-8 py-3 rounded-full bg-white text-neutral-900 font-semibold text-lg shadow-md hover:bg-neutral-200 transition"
          >
            Request a Booking
          </a>
        </section>
      </main>
    </div>
  );
}
