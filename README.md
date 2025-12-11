import React, { useState, useEffect } from 'react';
import { Mail, Phone, Car, Award, Code, Briefcase, GraduationCap, BookOpen, ChevronDown, ChevronUp, Trophy } from 'lucide-react';

export default function CVRubenGarcia() {
  const [expandedSection, setExpandedSection] = useState('experiencia');
  const [score, setScore] = useState(0);

  useEffect(() => {
    const interval = setInterval(() => {
      setScore(prev => (prev + 1) % 100);
    }, 3000);
    return () => clearInterval(interval);
  }, []);

  const toggleSection = (section) => {
    setExpandedSection(expandedSection === section ? '' : section);
  };

  const experiencias = [
    {
      cargo: "Gestor telefónico",
      empresa: "Servitelco - Ilunion",
      periodo: "2023/2024",
      descripcion: "Dar de alta y asesoramiento de servicios de Movistar Fusión Empresas, realización de centralitas automáticas y migrar clientes de ADSL a fibra óptica.",
      puntos: "⛹️ 95 pts"
    },
    {
      cargo: "Técnico de telecomunicaciones",
      empresa: "Varios teleoperadores",
      periodo: "2014-2021",
      descripcion: "Experiencia durante 2 años montando líneas ADSL y 7 años de fibra óptica para distintos teleoperadores.",
      puntos: "🏀 88 pts"
    },
    {
      cargo: "Formador",
      empresa: "Forum Andalucía",
      periodo: "2013-2014",
      descripcion: "Elaboración de material didáctico, impartición de clases, evolución y seguimiento de alumnos.",
      puntos: "🏆 92 pts"
    },
    {
      cargo: "Desarrollador de aplicaciones web",
      empresa: "Infoquery",
      periodo: "2008-2011",
      descripcion: "Desarrollo de aplicaciones web en la Consejería de Medio Ambiente, manejo y perfeccionamiento del tramitador Trew@ y la app Genista. Tecnología JAVA, STRUTS, HIBERNATE, ALFRESCO, XML.",
      puntos: "⛹️ 97 pts"
    },
    {
      cargo: "Desarrollador de aplicaciones web",
      empresa: "Guadaltel",
      periodo: "2007-2008",
      descripcion: "Desarrollo de aplicaciones web en la Consejería de Economía y Hacienda, manejo y perfeccionamiento del tramitador Trew@ y la app eCO. Tecnología JAVA, STRUTS, HIBERNATE, SUBVERSION.",
      puntos: "🏀 94 pts"
    },
    {
      cargo: "Desarrollador de aplicaciones",
      empresa: "Oversis",
      periodo: "2007",
      descripcion: "Desarrollo de aplicaciones y calidad de programas. Tecnología COBOL y DB2.",
      puntos: "⛹️ 90 pts"
    }
  ];

  const tecnologias = [
    "C", "C++", "Visual Basic", "PHP", "SQL", "PL-SQL", "MYSQL", "COBOL",
    "JAVA", "JSP", "HTML 5.0", "STRUTS", "HIBERNATE", "ALFRESCO", "XML",
    "SUBVERSION", "JAVASCRIPT", "MARKDOWN", "REACT"
  ];

  const cursos = [
    { nombre: "Desarrollo Web Frontend con React", horas: "250 horas", año: "2025", icono: "🏀" },
    { nombre: "Técnico de Diseño Gráfico", horas: "200 horas", año: "2012", icono: "⛹️" },
    { nombre: "Administrador de Bases de Datos", horas: "400 horas", año: "2011", icono: "🏀" },
    { nombre: "Lenguaje de programación COBOL orientado a entornos Mainframe", horas: "400 horas", año: "2002", icono: "⛹️" }
  ];

  return (
    <div className="min-h-screen bg-gradient-to-br from-orange-900 via-slate-900 to-orange-950 text-white relative overflow-hidden">
      {/* Cancha de baloncesto de fondo */}
      <div className="absolute inset-0 opacity-5">
        <svg viewBox="0 0 100 100" className="w-full h-full">
          <circle cx="50" cy="50" r="15" fill="none" stroke="white" strokeWidth="0.5"/>
          <line x1="0" y1="50" x2="100" y2="50" stroke="white" strokeWidth="0.3"/>
          <line x1="50" y1="0" x2="50" y2="100" stroke="white" strokeWidth="0.3"/>
          <rect x="0" y="35" width="15" height="30" fill="none" stroke="white" strokeWidth="0.3"/>
          <rect x="85" y="35" width="15" height="30" fill="none" stroke="white" strokeWidth="0.3"/>
        </svg>
      </div>

      {/* Header con tema de baloncesto */}
      <header className="bg-gradient-to-r from-orange-600 via-orange-700 to-orange-800 shadow-2xl border-b-4 border-orange-500 relative">
        <div className="max-w-6xl mx-auto px-6 py-12">
          {/* Balones decorativos */}
          <div className="absolute top-4 right-4 text-6xl animate-bounce">🏀</div>
          <div className="absolute bottom-4 left-4 text-4xl opacity-50">⛹️</div>
          
          <div className="text-center relative z-10">
            <div className="mb-4">
              <span className="text-7xl">🏀</span>
            </div>
            <h1 className="text-5xl font-bold mb-2 animate-fade-in">Rubén García Colchero</h1>
            <p className="text-2xl text-orange-100 mb-2 font-bold">Programador y Formador</p>
            <p className="text-lg text-orange-200 italic mb-6">
              "Codificando victorias, un commit a la vez 🏆💻"
            </p>
            
            <div className="flex flex-wrap justify-center gap-6 text-sm">
              <div className="flex items-center gap-2 bg-white/10 px-4 py-2 rounded-full backdrop-blur-sm border-2 border-orange-400">
                <Phone size={16} />
                <span>658 038 913</span>
              </div>
              <div className="flex items-center gap-2 bg-white/10 px-4 py-2 rounded-full backdrop-blur-sm border-2 border-orange-400">
                <Mail size={16} />
                <span>rubeng.colchero@gmail.com</span>
              </div>
              <div className="flex items-center gap-2 bg-white/10 px-4 py-2 rounded-full backdrop-blur-sm border-2 border-orange-400">
                <Car size={16} />
                <span>Permiso B + Vehículo propio</span>
              </div>
            </div>
          </div>
        </div>
      </header>

      <div className="max-w-6xl mx-auto px-6 py-12 relative z-10">
        {/* Marcador deportivo - Resumen Profesional */}
        <section className="mb-12 bg-gradient-to-r from-slate-800 to-slate-900 backdrop-blur-sm rounded-2xl p-8 shadow-xl border-4 border-orange-500 relative overflow-hidden">
          <div className="absolute top-2 right-2 bg-orange-600 px-4 py-2 rounded-lg font-mono font-bold text-xl">
            MVP 🏆 {score}
          </div>
          <h2 className="text-3xl font-bold mb-4 flex items-center gap-3">
            <Trophy className="text-yellow-400" />
            Perfil del Jugador
          </h2>
          <p className="text-lg text-gray-200 leading-relaxed">
            Como un base que dirige el juego en la cancha, soy un <strong>desarrollador con 3 años de experiencia</strong> 
            que orquesta soluciones tecnológicas con precisión. Mi trayectoria incluye <strong>2 años en ADSL</strong> y 
            <strong> 7 años en fibra óptica</strong>, construyendo la infraestructura que conecta el mundo. 
            Como en el baloncesto, combino estrategia, trabajo en equipo y ejecución impecable. 
            Certificado de discapacidad reconocido - porque los verdaderos campeones superan cualquier obstáculo.
          </p>
        </section>

        {/* Experiencia Laboral - Estadísticas del Jugador */}
        <section className="mb-12 bg-gradient-to-r from-slate-800 to-slate-900 backdrop-blur-sm rounded-2xl p-8 shadow-xl border-4 border-orange-500">
          <button 
            onClick={() => toggleSection('experiencia')}
            className="w-full flex items-center justify-between text-3xl font-bold mb-6 hover:text-orange-400 transition-colors"
          >
            <div className="flex items-center gap-3">
              <Briefcase className="text-orange-400" />
              Estadísticas Profesionales 📊
            </div>
            {expandedSection === 'experiencia' ? <ChevronUp /> : <ChevronDown />}
          </button>
          
          {expandedSection === 'experiencia' && (
            <div className="space-y-6">
              {experiencias.map((exp, index) => (
                <div key={index} className="bg-gradient-to-r from-orange-900/30 to-slate-900/30 rounded-xl p-6 border-l-4 border-orange-500 hover:border-orange-400 hover:bg-orange-900/40 transition-all duration-300 relative">
                  <div className="absolute top-2 right-2 bg-orange-600 px-3 py-1 rounded-full text-sm font-bold">
                    {exp.puntos}
                  </div>
                  <h3 className="text-xl font-bold text-orange-300">{exp.cargo}</h3>
                  <p className="text-gray-300 font-semibold">{exp.empresa}</p>
                  <p className="text-sm text-gray-400 mb-3">⏱️ {exp.periodo}</p>
                  <p className="text-gray-200">{exp.descripcion}</p>
                </div>
              ))}
            </div>
          )}
        </section>

        {/* Tecnologías - Arsenal Técnico */}
        <section className="mb-12 bg-gradient-to-r from-slate-800 to-slate-900 backdrop-blur-sm rounded-2xl p-8 shadow-xl border-4 border-orange-500">
          <h2 className="text-3xl font-bold mb-6 flex items-center gap-3">
            <Code className="text-orange-400" />
            Arsenal Técnico 🎯
          </h2>
          <p className="text-gray-300 mb-6 italic">
            "Como un jugador versátil que domina múltiples posiciones, manejo diversos lenguajes y tecnologías"
          </p>
          <div className="flex flex-wrap gap-3">
            {tecnologias.map((tech, index) => (
              <span 
                key={index}
                className="bg-gradient-to-r from-orange-600 to-orange-800 px-4 py-2 rounded-full text-sm font-semibold shadow-lg hover:scale-110 hover:from-orange-500 hover:to-orange-700 transition-all duration-200 cursor-default border-2 border-orange-400"
              >
                {tech}
              </span>
            ))}
          </div>
        </section>

        {/* Educación */}
        <section className="mb-12 bg-gradient-to-r from-slate-800 to-slate-900 backdrop-blur-sm rounded-2xl p-8 shadow-xl border-4 border-orange-500">
          <h2 className="text-3xl font-bold mb-6 flex items-center gap-3">
            <GraduationCap className="text-orange-400" />
            Formación Base 🎓
          </h2>
          <div className="bg-gradient-to-r from-orange-900/30 to-slate-900/30 rounded-xl p-6 border-l-4 border-orange-500">
            <div className="text-4xl mb-3">🏀</div>
            <h3 className="text-xl font-bold text-orange-300">Técnico Superior en Desarrollo de Aplicaciones Informáticas</h3>
            <p className="text-gray-300">IES Julio Verne - Sevilla</p>
            <p className="text-sm text-gray-400">⏱️ Finalizado en 2005</p>
          </div>
        </section>

        {/* Cursos Complementarios - Entrenamientos Especiales */}
        <section className="mb-12 bg-gradient-to-r from-slate-800 to-slate-900 backdrop-blur-sm rounded-2xl p-8 shadow-xl border-4 border-orange-500">
          <button 
            onClick={() => toggleSection('cursos')}
            className="w-full flex items-center justify-between text-3xl font-bold mb-6 hover:text-orange-400 transition-colors"
          >
            <div className="flex items-center gap-3">
              <BookOpen className="text-orange-400" />
              Entrenamientos Especiales 🏋️
            </div>
            {expandedSection === 'cursos' ? <ChevronUp /> : <ChevronDown />}
          </button>
          
          {expandedSection === 'cursos' && (
            <div className="grid md:grid-cols-2 gap-4">
              {cursos.map((curso, index) => (
                <div key={index} className="bg-gradient-to-r from-orange-900/30 to-slate-900/30 rounded-xl p-5 hover:bg-orange-900/40 transition-all duration-300 border-2 border-orange-600">
                  <div className="text-3xl mb-2">{curso.icono}</div>
                  <h3 className="text-lg font-bold text-orange-300 mb-2">{curso.nombre}</h3>
                  <p className="text-gray-300">⏱️ {curso.horas}</p>
                  <p className="text-sm text-gray-400">📅 Año: {curso.año}</p>
                </div>
              ))}
            </div>
          )}
        </section>

        {/* Competencias - Habilidades de Equipo */}
        <section className="bg-gradient-to-r from-orange-600 via-orange-700 to-orange-800 rounded-2xl p-8 shadow-2xl border-4 border-orange-400">
          <h2 className="text-3xl font-bold mb-6 text-center flex items-center justify-center gap-3">
            <span className="text-4xl">🏆</span>
            Habilidades de MVP
            <span className="text-4xl">🏆</span>
          </h2>
          <div className="grid md:grid-cols-3 gap-6 text-center">
            <div className="bg-white/10 rounded-xl p-6 backdrop-blur-sm hover:bg-white/20 transition-all duration-300 border-2 border-orange-300">
              <div className="text-4xl mb-3">🎤</div>
              <h3 className="text-xl font-bold mb-2">Comunicación eficaz</h3>
              <p className="text-sm text-orange-100">Como un buen jugador, comunico claramente</p>
            </div>
            <div className="bg-white/10 rounded-xl p-6 backdrop-blur-sm hover:bg-white/20 transition-all duration-300 border-2 border-orange-300">
              <div className="text-4xl mb-3">⚡</div>
              <h3 className="text-xl font-bold mb-2">Iniciativa y proactividad</h3>
              <p className="text-sm text-orange-100">Siempre un paso adelante en el juego</p>
            </div>
            <div className="bg-white/10 rounded-xl p-6 backdrop-blur-sm hover:bg-white/20 transition-all duration-300 border-2 border-orange-300">
              <div className="text-4xl mb-3">🎯</div>
              <h3 className="text-xl font-bold mb-2">Persona resolutiva</h3>
              <p className="text-sm text-orange-100">Anoto cuando el equipo lo necesita</p>
            </div>
          </div>
        </section>
      </div>

      {/* Footer */}
      <footer className="bg-slate-900 py-8 text-center text-gray-400 border-t-4 border-orange-600">
        <div className="text-4xl mb-3">🏀💻</div>
        <p className="text-lg font-bold text-orange-400">© 2025 Rubén García Colchero</p>
        <p className="text-sm italic">"Programando como un MVP, jugando como un developer"</p>
      </footer>
    </div>
  );
}
