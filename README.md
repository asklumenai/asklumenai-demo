import { useState } from "react";
import { motion } from "framer-motion";
import { Button } from "@/components/ui/button";
import { Card, CardContent } from "@/components/ui/card";

export default function AskLumenAI() {
  const [page, setPage] = useState("home");

  const NavButton = ({ label, target }) => (
    <Button variant={page === target ? "default" : "ghost"} onClick={() => setPage(target)}>
      {label}
    </Button>
  );

  return (
    <div className="min-h-screen bg-gradient-to-b from-gray-900 to-black text-white font-sans">
      {/* Navbar */}
      <header className="flex justify-between items-center p-6 border-b border-gray-800">
        <motion.h1 initial={{ opacity: 0 }} animate={{ opacity: 1 }} className="text-2xl font-bold text-green-400">
          AskLumenAI
        </motion.h1>
        <nav className="flex gap-4">
          <NavButton label="Home" target="home" />
          <NavButton label="Vision" target="vision" />
          <NavButton label="Founder" target="founder" />
          <NavButton label="Funding" target="funding" />
          <NavButton label="Contact" target="contact" />
        </nav>
      </header>

      {/* Pages */}
      <main className="p-10 max-w-5xl mx-auto">
        {page === "home" && (
          <motion.div initial={{ opacity: 0 }} animate={{ opacity: 1 }}>
            <h2 className="text-4xl font-extrabold text-center mb-6">The Future of Real-Time AI Assistance</h2>
            <p className="text-center text-gray-300 mb-6">AskLumenAI combines video + audio AI to create the world’s most intuitive real-time assistant.</p>

            {/* Video Embed */}
            <div className="flex justify-center mb-6">
              <video controls className="rounded-2xl shadow-lg max-w-2xl">
                <source src="/AskLumenAI_Pitch.mp4" type="video/mp4" />
                Your browser does not support the video tag.
              </video>
            </div>

            <div className="flex justify-center">
              <Button className="bg-green-500 hover:bg-green-600 text-white px-6 py-3 rounded-xl text-lg">Join Private Beta</Button>
            </div>
          </motion.div>
        )}

        {page === "vision" && (
          <motion.div initial={{ x: 100, opacity: 0 }} animate={{ x: 0, opacity: 1 }}>
            <h2 className="text-3xl font-bold mb-4">Our Vision</h2>
            <p className="text-gray-300 mb-4">AI should not just answer — it should explain, guide, and connect in real-time. AskLumenAI is designed to become the most intuitive AI companion for knowledge, learning, and decision-making.</p>
            <p className="text-gray-300">We aim to scale globally, integrate multi-language support, and revolutionize how humans interact with AI.</p>
          </motion.div>
        )}

        {page === "founder" && (
          <motion.div initial={{ y: 50, opacity: 0 }} animate={{ y: 0, opacity: 1 }}>
            <h2 className="text-3xl font-bold mb-4">Meet the Founder</h2>
            <Card className="bg-gray-800 border border-gray-700">
              <CardContent className="p-6">
                <h3 className="text-2xl font-semibold text-green-400 mb-2">Venkatesh Mishra</h3>
                <p className="text-gray-300">The visionary behind AskLumenAI, Venkatesh is driven to redefine human–AI interaction. With a passion for design and innovation, he is building tools that empower people and reshape industries.</p>
              </CardContent>
            </Card>
          </motion.div>
        )}

        {page === "funding" && (
          <motion.div initial={{ scale: 0.9, opacity: 0 }} animate={{ scale: 1, opacity: 1 }}>
            <h2 className="text-3xl font-bold mb-4">Funding Opportunity</h2>
            <p className="text-gray-300 mb-6">AskLumenAI is raising a pre-seed round of <span className="text-green-400 font-bold">$50K–$150K</span> to build and scale the first real-time video + audio AI assistant. Join us as an early backer of a game-changing product.</p>
            <Button className="bg-green-500 hover:bg-green-600 text-white px-6 py-3 rounded-xl text-lg" asChild>
              <a href="mailto:founder.asklumen.ai@gmail.com">Contact Founder</a>
            </Button>
          </motion.div>
        )}

        {page === "contact" && (
          <motion.div initial={{ opacity: 0 }} animate={{ opacity: 1 }}>
            <h2 className="text-3xl font-bold mb-4">Get in Touch</h2>
            <form className="flex flex-col gap-4 max-w-md">
              <input type="text" placeholder="Name" className="p-3 rounded-lg bg-gray-800 border border-gray-700" />
              <input type="email" placeholder="Email" className="p-3 rounded-lg bg-gray-800 border border-gray-700" />
              <textarea placeholder="Message" className="p-3 rounded-lg bg-gray-800 border border-gray-700 h-32"></textarea>
              <Button className="bg-green-500 hover:bg-green-600 text-white px-6 py-3 rounded-xl text-lg">Send Message</Button>
            </form>
          </motion.div>
        )}
      </main>

      {/* Footer */}
      <footer className="border-t border-gray-800 p-6 text-center text-gray-500">
        © {new Date().getFullYear()} AskLumenAI. Built by Venkatesh Mishra.
      </footer>
    </div>
  );
}
