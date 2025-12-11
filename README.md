import React, { useState, useEffect } from 'react';
import { Code, Dribbble, Mail, Phone, Award, Briefcase, GraduationCap, Zap } from 'lucide-react';

const BasketballCV = () => {
  const [score, setScore] = useState(0);
  const [activeSection, setActiveSection] = useState('sobre-mi');
  const [ballPosition, setBallPosition] = useState({ x: 50, y: 20 });

  useEffect(() => {
    const interval = setInterval(() => {
      setBallPosition({
        x: 20 + Math.random() * 60,
        y: 10 + Math.random() * 15
      });
    }, 3000);
    return () => clearInterval(interval);
  }, []);

  const handleSectionClick = (section) => {
    setActiveSection(section);
    setScore(score + 2);
  };

  const sections = [
    { id: 'sobre-mi', name: 'Sobre Mí', icon: Dribbble },
    { id: 'experiencia', name: 'Experiencia', icon: Briefcase },
    { id: 'educacion', name: 'Educación', icon: GraduationCap },
    { id: 'habilidades', name: 'Habilidades', icon: Code },
  ];

  return (
    <div className="min-h-screen bg-gradient-to-br from-orange-600 via-red-700 to-purple-900 text-white p-8 relative overflow-hidden">
      {/* Balón de baloncesto animado */}
      <div 
        className="absolute w-16 h-16 bg-orange-500 rounded-full shadow-2xl transition-all duration-3000 ease-in-out"
        style={{
          left: `${ballPosition.x}%`,
          top: `${ballPosition.y}%`,
          boxShadow: '0 0 40px rgba(255, 165, 0, 0.6)',
          background: 'radial-gradient(circle at 30% 30%, #ff8c42, #ff6b35)'
        }}
      >
        <div className="w-full h-full flex items-center justify-center text-2xl">🏀</div>
      </div>

      {/* Marcador */}
      <div className="absolute top-8 right-8 bg-black bg-opacity-60 px-6 py-3 rounded-lg backdrop-blur-sm">
        <div className="text-xs text-orange-400 font-bold">PUNTOS</div>
        <div className="text-4xl font-bold text-white">{score}</div>
      </div>

      {/* Header */}
      <div className="max-w-6xl mx-auto relative z-10">
        <div className="text-center mb-12 animate-fade-in">
          <div className="flex items-center justify-center gap-4 mb-4">
            <Code className="w-12 h-12 text-orange-400" />
            <h1 className="text-6xl font-bold bg-clip-text text-transparent bg-gradient-to-r from-orange-400 to-yellow-300">
              RUBÉN GARCÍA COLCHERO
            </h1>
            <Dribbble className="w-12 h-12 text-orange-400" />
          </div>
          <p className="text-2xl text-orange-300 font-semibold mb-4">
            PROGRAMADOR | FORMADOR | APASIONADO DEL BALONCESTO
          </p>
          <div className="flex justify-center gap-6 text-sm">
            <div className="flex items-center gap-2 bg-black bg-opacity-40 px-4 py-2 rounded-full">
              <Phone className="w-4 h-4" />
              <span>658 038 913</span>
            </div>
            <div className="flex items-center gap-2 bg-black bg-opacity-40 px-4 py-2 rounded-full">
              <Mail className="w-4 h-4" />
              <span>rubeng.colchero@gmail.com</span>
            </div>
          </div>
        </div>

        {/* Navegación tipo cancha de baloncesto */}
        <div className="flex justify-center gap-4 mb-8">
          {sections.map((section) => (
            <button
              key={section.id}
              onClick={() => handleSectionClick(section.id)}
              className={`flex items-center gap-2 px-6 py-3 rounded-full font-bold transition-all transform hover:scale-110 ${
                activeSection === section.id
                  ? 'bg-orange-500 shadow-lg shadow-orange-500/50'
                  : 'bg-black bg-opacity-40 hover:bg-orange-600'
              }`}
            >
              <section.icon className="w-5 h-5" />
              {section.name}
            </button>
          ))}
        </div>

        {/* Contenido */}
        <div className="bg-black bg-opacity-40 backdrop-blur-md rounded-3xl p-8 shadow-2xl border-4 border-orange-500">
          {activeSection === 'sobre-mi' && (
            <div className="animate-fade-in">
              <h2 className="text-3xl font-bold mb-6 flex items-center gap-3">
                <Dribbble className="w-8 h-8 text-orange-400" />
                Perfil del Jugador
              </h2>
              <div className="space-y-4 text-lg">
                <p className="leading-relaxed">
                  Desarrollador con <span className="text-orange-400 font-bold">3 años de experiencia</span> en la cancha del desarrollo de aplicaciones, 
                  dominando múltiples lenguajes de programación como un base que controla el juego.
                </p>
                <p className="leading-relaxed">
                  Además, cuento con <span className="text-orange-400 font-bold">2 años montando ADSL</span> y <span className="text-orange-400 font-bold">7 años en fibra óptica</span>, 
                  conectando el mundo como se conectan las jugadas en la cancha.
                </p>
                <div className="flex gap-4 mt-6">
                  <div className="bg-orange-500 bg-opacity-20 px-6 py-4 rounded-lg flex-1">
                    <div className="text-orange-400 font-bold text-sm">POSICIÓN</div>
                    <div className="text-2xl font-bold">Full Stack Developer</div>
                  </div>
                  <div className="bg-orange-500 bg-opacity-20 px-6 py-4 rounded-lg flex-1">
                    <div className="text-orange-400 font-bold text-sm">EQUIPO</div>
                    <div className="text-2xl font-bold">Disponible</div>
                  </div>
                </div>
              </div>
            </div>
          )}

          {activeSection === 'experiencia' && (
            <div className="animate-fade-in">
              <h2 className="text-3xl font-bold mb-6 flex items-center gap-3">
                <Briefcase className="w-8 h-8 text-orange-400" />
                Trayectoria Profesional
              </h2>
              <div className="space-y-6">
                {[
                  { year: '2023-2024', team: 'Servitelco - Ilunion', role: 'Gestor Telefónico', tech: 'Movistar Fusión, Centralitas, ADSL a Fibra' },
                  { year: '2014-2021', team: 'Varios Teleoperadores', role: 'Técnico Telecomunicaciones', tech: '2 años ADSL + 7 años Fibra Óptica' },
                  { year: '2013-2014', team: 'Forum Andalucía', role: 'Formador', tech: 'Material didáctico, Clases, Seguimiento alumnos' },
                  { year: '2008-2011', team: 'Infoquery', role: 'Desarrollador Web', tech: 'JAVA, STRUTS, HIBERNATE, ALFRESCO, XML' },
                  { year: '2007-2008', team: 'Guadaltel', role: 'Desarrollador Web', tech: 'JAVA, STRUTS, HIBERNATE, SUBVERSION' },
                  { year: '2007', team: 'Oversis', role: 'Desarrollador', tech: 'COBOL, DB2' },
                ].map((exp, i) => (
                  <div key={i} className="bg-gradient-to-r from-orange-500 to-red-600 bg-opacity-20 p-6 rounded-xl border-l-4 border-orange-400 hover:scale-105 transition-transform">
                    <div className="flex justify-between items-start mb-2">
                      <div>
                        <h3 className="text-2xl font-bold text-orange-300">{exp.team}</h3>
                        <p className="text-xl text-white">{exp.role}</p>
                      </div>
                      <span className="bg-orange-500 px-4 py-2 rounded-full font-bold">{exp.year}</span>
                    </div>
                    <p className="text-orange-200 mt-2">{exp.tech}</p>
                  </div>
                ))}
              </div>
            </div>
          )}

          {activeSection === 'educacion' && (
            <div className="animate-fade-in">
              <h2 className="text-3xl font-bold mb-6 flex items-center gap-3">
                <GraduationCap className="w-8 h-8 text-orange-400" />
                Formación & Entrenamientos
              </h2>
              <div className="space-y-6">
                <div className="bg-orange-500 bg-opacity-20 p-6 rounded-xl border-2 border-orange-400">
                  <h3 className="text-2xl font-bold text-orange-300 mb-2">Técnico Superior en Desarrollo de Aplicaciones</h3>
                  <p className="text-lg">IES Julio Verne (Sevilla) - 2005</p>
                </div>
                
                <div className="grid grid-cols-2 gap-4">
                  {[
                    { name: 'Desarrollo Web Frontend con React', hours: '250h', year: '2025' },
                    { name: 'Técnico de Diseño Gráfico', hours: '200h', year: '2012' },
                    { name: 'Administrador de Bases de Datos', hours: '400h', year: '2011' },
                    { name: 'COBOL - Entornos Mainframe', hours: '400h', year: '2002' },
                  ].map((curso, i) => (
                    <div key={i} className="bg-black bg-opacity-40 p-4 rounded-lg hover:bg-orange-600 hover:bg-opacity-30 transition-all">
                      <h4 className="font-bold text-orange-300">{curso.name}</h4>
                      <div className="flex justify-between mt-2 text-sm">
                        <span className="text-orange-400">{curso.hours}</span>
                        <span>{curso.year}</span>
                      </div>
                    </div>
                  ))}
                </div>
              </div>
            </div>
          )}

          {activeSection === 'habilidades' && (
            <div className="animate-fade-in">
              <h2 className="text-3xl font-bold mb-6 flex items-center gap-3">
                <Zap className="w-8 h-8 text-orange-400" />
                Arsenal Técnico
              </h2>
              <div className="space-y-6">
                <div>
                  <h3 className="text-xl font-bold text-orange-300 mb-4">Lenguajes & Tecnologías</h3>
                  <div className="flex flex-wrap gap-3">
                    {['C', 'C++', 'Visual Basic', 'PHP', 'SQL', 'PL-SQL', 'MYSQL', 'COBOL', 'JAVA', 'JSP', 
                      'HTML5', 'STRUTS', 'HIBERNATE', 'ALFRESCO', 'XML', 'SUBVERSION', 'JAVASCRIPT', 'MARKDOWN', 'REACT'].map((tech) => (
                      <span key={tech} className="bg-orange-500 px-4 py-2 rounded-full font-bold hover:bg-orange-400 hover:scale-110 transition-transform cursor-pointer">
                        {tech}
                      </span>
                    ))}
                  </div>
                </div>

                <div>
                  <h3 className="text-xl font-bold text-orange-300 mb-4">Competencias Clave</h3>
                  <div className="grid grid-cols-3 gap-4">
                    {[
                      { name: 'Comunicación Eficaz', icon: '🎯' },
                      { name: 'Iniciativa y Proactividad', icon: '🚀' },
                      { name: 'Persona Resolutiva', icon: '💡' },
                    ].map((comp) => (
                      <div key={comp.name} className="bg-gradient-to-br from-orange-500 to-red-600 p-6 rounded-xl text-center hover:scale-105 transition-transform">
                        <div className="text-4xl mb-2">{comp.icon}</div>
                        <div className="font-bold">{comp.name}</div>
                      </div>
                    ))}
                  </div>
                </div>

                <div className="bg-orange-500 bg-opacity-20 p-6 rounded-xl border-2 border-orange-400">
                  <h3 className="text-xl font-bold text-orange-300 mb-2">Información Adicional</h3>
                  <div className="space-y-2">
                    <p>✅ Permiso de conducir: Clase B, vehículo propio</p>
                    <p>✅ Certificado de discapacidad</p>
                  </div>
                </div>
              </div>
            </div>
          )}
        </div>

        {/* Footer */}
        <div className="text-center mt-8 text-orange-300">
          <p className="text-sm">🏀 "El código es como el baloncesto: requiere práctica, trabajo en equipo y pasión" 🏀</p>
        </div>
      </div>

      <style jsx>{`
        @keyframes fade-in {
          from { opacity: 0; transform: translateY(20px); }
          to { opacity: 1; transform: translateY(0); }
        }
        .animate-fade-in {
          animation: fade-in 0.5s ease-out;
        }
      `}</style>
    </div>
  );
};

export default BasketballCV;
