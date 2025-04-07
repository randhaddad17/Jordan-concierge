import React from "react";
import { motion } from "framer-motion";

export default function Home() {
  return (
    <main className="min-h-screen bg-gradient-to-br from-blue-100 to-white flex items-center justify-center p-6">
      <motion.div
        initial={{ opacity: 0, y: 40 }}
        animate={{ opacity: 1, y: 0 }}
        transition={{ duration: 0.6 }}
        className="bg-white shadow-2xl rounded-2xl p-8 max-w-md w-full text-center space-y-4"
      >
        <h1 className="text-2xl font-bold text-blue-700">
          🚐 رحلتك بدأت!
        </h1>
        <p className="text-gray-600">
          شكراً لاستخدامك خدمتنا. وجهتك القادمة هي:
        </p>
        <div className="bg-blue-50 rounded-xl p-4 shadow-inner text-gray-800 font-semibold">
          📍 البترا، وادي موسى
        </div>
        <p className="text-sm text-gray-500">
          سيتم توصيلك خلال <strong>3 ساعات</strong>. نحن هنا لنجعل تجربتك مريحة وآمنة.
        </p>
        <button className="mt-4 bg-blue-600 text-white px-4 py-2 rounded-xl shadow hover:bg-blue-700 transition">
          تتبع رحلتي
        </button>
      </motion.div>
    </main>
  );
}
