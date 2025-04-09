// src/App.jsx
import { useState } from "react";
import { Cat } from "./components/Cat";
import catsData from "./data/cats.json";
import BirthdayCard from "./components/BirthdayCard";

export default function App() {
  const [foundCats, setFoundCats] = useState([]);

  const handleFind = (id) => {
    if (!foundCats.includes(id)) {
      setFoundCats([...foundCats, id]);
    }
  };

  return (
    <div className="min-h-screen bg-pink-50 p-4">
      <h1 className="text-4xl font-bold text-center mb-4">🎉 Find the Cat 🎂</h1>
      <p className="text-center text-lg mb-6">Click all the cats to unlock your birthday card!</p>
      <div className="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 gap-4">
        {catsData.map((cat, index) => (
          <Cat key={cat.id} data={cat} onFind={handleFind} found={foundCats.includes(cat.id)} isLast={index === catsData.length - 1} />
        ))}
      </div>

      {foundCats.length === catsData.length && (
        <div className="mt-8">
          <BirthdayCard />
        </div>
      )}
    </div>
  );
}
