# aira-date-invite
import { useState } from "react";
import { Button } from "@/components/ui/button";
import { Heart } from "lucide-react";
import { motion } from "framer-motion";

export default function AiraDateInvite() {
  const [step, setStep] = useState(0);

  const handleYes = () => setStep(2);
  const handleNo = () => setStep(1);

  return (
    <div className="min-h-screen bg-pink-100 flex flex-col items-center justify-center p-6 text-center">
      {step === 0 && (
        <motion.div
          initial={{ opacity: 0, scale: 0.8 }}
          animate={{ opacity: 1, scale: 1 }}
          transition={{ duration: 0.8 }}
          className="bg-white rounded-2xl shadow-xl p-8 max-w-md w-full border-4 border-pink-300 relative"
        >
          <div className="absolute -top-5 left-1/2 transform -translate-x-1/2">
            <Heart className="text-pink-500 w-10 h-10 animate-bounce" fill="pink" />
          </div>
          <h1 className="text-2xl font-bold text-pink-600 mb-4">
            Hi Aira! 💖
          </h1>
          <p className="text-lg text-gray-700 mb-6">
            Would you make my day and go on a date with me?
          </p>
          <div className="flex justify-center gap-4">
            <Button onClick={handleYes} className="bg-pink-500 text-white hover:bg-pink-600 rounded-full px-6 py-2 text-lg">
              Yes 💘
            </Button>
            <Button onClick={handleNo} className="bg-white text-pink-500 border-2 border-pink-500 hover:bg-pink-50 rounded-full px-6 py-2 text-lg">
              No 💔
            </Button>
          </div>
        </motion.div>
      )}

      {step === 1 && (
        <motion.div
          initial={{ opacity: 0, y: 30 }}
          animate={{ opacity: 1, y: 0 }}
          transition={{ duration: 0.5 }}
          className="bg-white rounded-2xl shadow-lg p-6 max-w-md w-full mt-4 border-4 border-pink-200"
        >
          <p className="text-pink-600 text-xl mb-4">
            Oh no... that can’t be right 🥺 Let's try that again~
          </p>
          <Button
            onClick={() => setStep(0)}
            className="bg-pink-400 text-white hover:bg-pink-500 rounded-full px-5 py-2 text-lg"
          >
            Okay 💓
          </Button>
        </motion.div>
      )}

      {step === 2 && (
        <motion.div
          initial={{ opacity: 0, scale: 0.8 }}
          animate={{ opacity: 1, scale: 1 }}
          transition={{ duration: 0.8 }}
          className="bg-white rounded-2xl shadow-2xl p-8 max-w-md w-full border-4 border-pink-300 text-pink-700"
        >
          <h2 className="text-2xl font-bold mb-4">Yay!! 💞</h2>
          <p className="text-lg">I can't wait to see you on our date, Aira. You just made me the happiest person alive! 💐✨</p>
        </motion.div>
      )}
    </div>
  );
}
