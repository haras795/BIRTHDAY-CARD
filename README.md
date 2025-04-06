import React from "react";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { motion } from "framer-motion";

const pages = [
  {
    title: "Happy Birthday, Maya!",
    content: `Surprise!\nThis magical page is made just for you.\nSo sit back, smile, and i hope you like it.\nBecause you, Mayo, are something else.`,
    button: "Aww, keep going!"
  },
  {
    title: "Hey Mayo Gayo...",
    content: `Sometimes you may not know it but .\nYour laugh? Addictive.\nYour love? My favorite thing ever.`,
    button: "Tell me more!"
  },
  {
    title: "Just so you know...",
    content: `Every day with you is a gift.\nAnd today, on *your* day, I just wanna remind you:\nYou are appreciated, and oh-so-loved.\nBy me. Always.`,
    button: "Next one please!"
  },
  {
    title: "A little promise",
    content: `Through the giggles, the stubborn debates, and all the cozy silences—\nI’ll be right here. Hyping you up all the time. Being your biggest fan, and I'll always be proud of you\nYou’ve got me, Mayo. Fully.`,
    button: "Final part!"
  },
  {
    title: "To My Favorite Human",
    content: `Happy Birthday, Maya.\nThank you for existing, for letting me love you.
Now go I hope get to eat all the cake.\nI can't believe i get to be around on your birthday especially your 18th. Mayo Gayo.\nP.S. I love you more than words ever could.`,
    button: "Read it again!"
  }
];

export default function BirthdayLetter() {
  const [page, setPage] = React.useState(0);

  const nextPage = () => {
    setPage((prev) => (prev + 1) % pages.length);
  };

  return (
    <div className="flex min-h-screen items-center justify-center bg-yellow-100 p-4">
      <motion.div
        className="max-w-xl w-full"
        initial={{ opacity: 0, y: 30 }}
        animate={{ opacity: 1, y: 0 }}
        transition={{ duration: 0.5 }}
      >
        <Card className="rounded-2xl shadow-xl">
          <CardContent className="p-6 text-center space-y-4">
            <h1 className="text-2xl font-bold text-yellow-700">
              {pages[page].title}
            </h1>
            <p className="whitespace-pre-wrap text-gray-800">
              {pages[page].content}
            </p>
            <Button onClick={nextPage} className="bg-yellow-500 hover:bg-yellow-600 text-white">
              {pages[page].button}
            </Button>
          </CardContent>
        </Card>
      </motion.div>
    </div>
  );
}
