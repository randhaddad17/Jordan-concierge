
'use client';
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { Input } from "@/components/ui/input";
import { MapPin, CalendarDays, Music, Info, Smile, Sun, Moon } from "lucide-react";
import { useState } from "react";
import { motion } from "framer-motion";

export default function TouristTripUI() {
  const [darkMode, setDarkMode] = useState(false);

  return (
    <div className={darkMode ? "bg-gray-900 text-white min-h-screen" : "bg-white text-black min-h-screen"}>
      <div className="flex justify-end p-4">
        <Button variant="ghost" onClick={() => setDarkMode(!darkMode)}>
          {darkMode ? <Sun className="ml-2" /> : <Moon className="ml-2" />}
          {darkMode ? "وضع النهار" : "الوضع الليلي"}
        </Button>
      </div>
      <div className="grid grid-cols-1 lg:grid-cols-2 gap-6 p-6">
        <div className="space-y-4">
          <motion.h1 initial={{ opacity: 0, y: -20 }} animate={{ opacity: 1, y: 0 }} className="text-2xl font-bold text-right">
            مرحباً أحمد!
          </motion.h1>
          <p className="text-right text-gray-600 dark:text-gray-300">
            رحلتك إلى البتراء ستبدأ خلال:
            <span className="font-semibold text-red-600 dark:text-yellow-400"> 3 ساعات و 25 دقيقة</span>
          </p>

          <Card>
            <CardContent className="p-4 space-y-2 text-right">
              <div className="flex items-center gap-2 justify-end">
                <MapPin className="text-primary" />
                <span>المسار: عمّان → مادبا → البتراء</span>
              </div>
              <div className="flex items-center gap-2 justify-end">
                <CalendarDays className="text-primary" />
                <span>الانطلاق: 2:30 مساءً</span>
              </div>
              <div className="mt-2">
                <iframe
                  src="https://www.google.com/maps/embed?..."
                  width="100%"
                  height="200"
                  allowFullScreen
                  loading="lazy"
                  className="rounded-xl"
                ></iframe>
              </div>
            </CardContent>
          </Card>

          <Card>
            <CardContent className="p-4 text-right">
              <h2 className="font-bold mb-2">اختر ترفيه الرحلة:</h2>
              <div className="grid grid-cols-2 gap-2">
                <Button variant="outline"><Music className="ml-2" /> موسيقى هادئة</Button>
                <Button variant="outline"><Music className="ml-2" /> موسيقى محلية</Button>
                <Button variant="outline"><Smile className="ml-2" /> ألعب Trivia</Button>
                <Button variant="outline"><Info className="ml-2" /> دليل صوتي</Button>
              </div>
            </CardContent>
          </Card>

          <Card>
            <CardContent className="p-4 text-right">
              <h2 className="font-bold mb-2">معلومات مفيدة:</h2>
              <ul className="list-disc list-inside text-sm">
                <li>درجة الحرارة المتوقعة: 23°</li>
                <li>ننصح بارتداء حذاء مريح</li>
                <li>الكاميرا ضرورية 😄</li>
              </ul>
            </CardContent>
          </Card>
        </div>

        <div className="space-y-4">
          <Card>
            <CardContent className="p-4 text-right">
              <h2 className="font-bold mb-2">تعرف على سائقك:</h2>
              <p>الاسم: محمد العجارمة</p>
              <p>اللغات: عربي، إنجليزي</p>
              <p>نبذة: يحب مشاركة القصص عن الصحراء والبدو</p>
            </CardContent>
          </Card>

          <Card>
            <CardContent className="p-4 text-right">
              <h2 className="font-bold mb-2">هل ترغب بإضافة ضيافة؟</h2>
              <div className="flex gap-2">
                <Button variant="secondary">نعم، تمر وكتيب</Button>
                <Button variant="ghost">لا، شكراً</Button>
              </div>
            </CardContent>
          </Card>

          <Card>
            <CardContent className="p-4 text-right">
              <h2 className="font-bold mb-2">تواصل سريع:</h2>
              <Input placeholder="اكتب سؤالك أو استفسارك هنا..." className="mb-2" />
              <Button className="w-full">إرسال للدعم</Button>
            </CardContent>
          </Card>
        </div>
      </div>
    </div>
  );
}
