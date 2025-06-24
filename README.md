import { Card, CardContent } from "@/components/ui/card";
import { motion } from "framer-motion";
import { PhoneCall, Mail, MessageCircle, Smartphone } from "lucide-react";

const watches = [
  {
    model: "Rolex Submariner Date 16610",
    price: "₪50,000",
    description: "Classic stainless steel diver's watch with timeless appeal.",
    img: "https://images.bobswatches.com/rolex-submariner-16610-stainless-steel-oyster.jpg"
  },
  {
    model: "Omega Speedmaster Professional",
    price: "₪30,000",
    description: "The legendary chronograph worn on the moon.",
    img: "https://cdn2.chrono24.com/images/uhren/26859102-8ayc5e5obhlbcn2p3pmv7lnt-ExtraLarge.jpg"
  },
  // הוסף כאן את שאר השעונים שלך
];

function ContactSection() {
  return (
    <section className="max-w-5xl mx-auto mt-16 mb-10 px-4">
      <h2 className="text-3xl font-bold mb-10 text-center text-[#5f7b55]">צור קשר</h2>
      <div className="grid grid-cols-2 md:grid-cols-4 gap-6">
        <div className="flex flex-col items-center p-6 bg-white border-4 border-[#d4b167] rounded-xl shadow-lg hover:shadow-[#e8d6a3] transition cursor-pointer">
          <PhoneCall className="text-[#b79c67] w-14 h-14 mb-4" />
          <h3 className="text-xl font-semibold text-[#3e503c] mb-2">טלפון</h3>
          <a href="tel:+972501234567" className="text-[#3e503c] hover:underline">050-1234567</a>
        </div>
        <div className="flex flex-col items-center p-6 bg-white border-4 border-[#d4b167] rounded-xl shadow-lg hover:shadow-[#e8d6a3] transition cursor-pointer">
          <Mail className="text-[#b79c67] w-14 h-14 mb-4" />
          <h3 className="text-xl font-semibold text-[#3e503c] mb-2">אימייל</h3>
          <a href="mailto:info@segevwatches.com" className="text-[#3e503c] hover:underline">info@segevwatches.com</a>
        </div>
        <div className="flex flex-col items-center p-6 bg-white border-4 border-[#d4b167] rounded-xl shadow-lg hover:shadow-[#e8d6a3] transition cursor-pointer">
          <Smartphone className="text-[#b79c67] w-14 h-14 mb-4" />
          <h3 className="text-xl font-semibold text-[#3e503c] mb-2">וואטסאפ</h3>
          <a href="https://wa.me/972501234567" target="_blank" rel="noreferrer" className="text-[#3e503c] hover:underline">לחצו לפתוח שיחה</a>
        </div>
        <div className="flex flex-col items-center p-6 bg-white border-4 border-[#d4b167] rounded-xl shadow-lg hover:shadow-[#e8d6a3] transition cursor-pointer">
          <MessageCircle className="text-[#b79c67] w-14 h-14 mb-4" />
          <h3 className="text-xl font-semibold text-[#3e503c] mb-2">צ׳אט</h3>
          <button className="px-6 py-2 border border-[#b79c67] rounded-md text-[#3e503c] hover:bg-[#b79c67] hover:text-white transition">פתח צ׳אט</button>
        </div>
      </div>
    </section>
  );
}

export default function HomePage() {
  return (
    <div className="min-h-screen bg-gradient-to-b from-[#f8f6f2] via-[#f5f2ea] to-[#ebe7dd] text-[#1f1f1f] font-serif bg-fixed bg-cover" style={{ backgroundImage: "url('/images/texture-light.jpg')" }}>
      <div className="backdrop-blur-sm bg-white/60 max-w-7xl mx-auto py-20 px-4">
        <motion.h1 initial={{ opacity: 0, y: -20 }} animate={{ opacity: 1, y: 0 }} transition={{ duration: 0.6 }} className="text-4xl md:text-6xl font-bold text-center mb-4 text-[#5f7b55]">
          Segev Watches
        </motion.h1>
        <p className="text-center text-lg md:text-xl text-[#5a5a5a] mb-12">Curated timepieces that speak the language of heritage, elegance, and discretion.</p>
        <div className="grid md:grid-cols-3 gap-8 mb-20">
          {watches.map((watch, index) => (
            <Card key={index} className="rounded-2xl shadow-lg bg-white border border-[#e6e4da]">
              <CardContent className="p-6">
                <div className="bg-white border-2 border-[#d4b167] rounded-xl overflow-hidden mb-4 h-52 flex items-center justify-center shadow-md shadow-[#e8d6a3]">
                  <img src={watch.img} alt={watch.model} className="max-h-full object-contain transition-transform duration-300 hover:scale-105" />
                </div>
                <h3 className="text-xl font-semibold text-[#3e503c] mb-1">{watch.model}</h3>
                <p className="text-sm text-gray-600 mb-2">{watch.description}</p>
                <p className="text-md font-medium text-[#b79c67]">{watch.price}</p>
              </CardContent>
            </Card>
          ))}
        </div>
        <ContactSection />
      </div>
    </div>
  );
}
