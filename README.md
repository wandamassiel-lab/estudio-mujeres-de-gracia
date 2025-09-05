import React, { useState } from 'react';

const App = () => {
  const [view, setView] = useState('home');
  const [currentWeek, setCurrentWeek] = useState(1);
  const [notes, setNotes] = useState('');

  // Study data
  const studyData = [
    {
      week: 1,
      title: 'INTRODUCCIÓN',
      reading: 'Introducción del libro',
      centralIdea: 'Sentar las bases para entender el desierto como un lugar de encuentro y transformación, no solo de sufrimiento.',
      keyVerse: '“Porque el Señor hará esto para que tu vida sea como un huerto bien regado.” - Jeremías 31:12',
      reflectionQuestions: [
        '¿Qué esperas de este estudio y cómo te ha preparado Dios para recibir Su Palabra en esta temporada?',
        '¿Sientes que el desierto espiritual es un castigo o una oportunidad? ¿Por qué?',
        '¿Qué prejuicios tienes sobre la "vida en el desierto" que necesitas entregar a Dios?'
      ],
      prayerPrompt: 'Ora pidiendo a Dios que abra tu corazón y tu mente para entender el propósito de este estudio.'
    },
    {
      week: 2,
      title: 'CAPÍTULO 1: El alma en el desierto',
      reading: 'Capítulo 1',
      centralIdea: 'Identificar las señales de la sequía espiritual en nuestra vida y comprender que el desierto puede ser un lugar de encuentro con Dios.',
      keyVerse: '“El alma del perezoso desea, y nada alcanza; mas el alma de los diligentes será engordada.” - Proverbios 13:4',
      reflectionQuestions: [
        '¿Cómo se manifiesta la sequía espiritual en tu vida actualmente?',
        'Comparte una experiencia en la que sentiste a Dios más cerca en medio de una dificultad.',
        '¿Qué "ídolos" o distracciones te impiden buscar a Dios en tu desierto?'
      ],
      prayerPrompt: 'Ora pidiendo a Dios que te revele las áreas de sequía en tu corazón y te dé la valentía para enfrentarlas con fe.'
    },
    {
      week: 3,
      title: 'CAPÍTULO 2: Cómo llegamos hasta allí',
      reading: 'Capítulo 2',
      centralIdea: 'Descubrir las disciplinas espirituales y las promesas de Dios como fuentes de sustento y renovación en tiempos de aridez.',
      keyVerse: '“Porque yo sé los planes que tengo para ustedes, declara el Señor, planes de bienestar y no de calamidad, para darles un futuro y una esperanza.” - Jeremías 29:11',
      reflectionQuestions: [
        '¿Qué factores o decisiones te llevaron al desierto espiritual en el que te encuentras hoy?',
        '¿Puedes identificar un momento en el que tomaste un desvío que te alejó de Dios?',
        '¿Cómo puedes usar este conocimiento para guiar a otros que podrían estar en el mismo camino?'
      ],
      prayerPrompt: 'Pide al Espíritu Santo que te dé la humildad para reconocer tus errores y la gracia para volver al camino de Dios.'
    },
    {
      week: 4,
      title: 'CAPÍTULO 3: El camino del pecado',
      reading: 'Capítulo 3',
      centralIdea: 'Aprender a caminar por fe en el desierto, confiando en que Dios tiene un propósito para esta temporada y que nos está moldeando a la imagen de Cristo.',
      keyVerse: '“Si confesamos nuestros pecados, Él es fiel y justo para perdonarnos nuestros pecados y para limpiarnos de toda maldad.” - 1 Juan 1:9',
      reflectionQuestions: [
        '¿Qué pecado o área de tu vida se ha convertido en un obstáculo para tu relación con Dios?',
        '¿Qué pasos prácticos puedes tomar esta semana para arrepentirte y buscar la pureza?',
        '¿Cómo te hace sentir la promesa de que, al confesar, Dios te perdona y te limpia?'
      ],
      prayerPrompt: 'Ora pidiendo a Dios por un corazón arrepentido y la fortaleza para alejarte del pecado que te impide crecer.'
    },
    {
      week: 5,
      title: 'CAPÍTULO 4: Volver a Dios',
      reading: 'Capítulo 4',
      centralIdea: 'Celebrar la obra de Dios que nos hace florecer aun en la tierra más árida, y aprender a vivir en una continua dependencia de Su gracia.',
      keyVerse: '“Acerquémonos, pues, confiadamente al trono de la gracia, para alcanzar misericordia y hallar gracia para el oportuno socorro.” - Hebreos 4:16',
      reflectionQuestions: [
        '¿Qué significa para ti "volver a Dios" cuando te sientes tan lejos?',
        '¿Qué ha sido lo más difícil de volver a la comunión con Él?',
        '¿De qué manera puedes abrir tu corazón para recibir Su gracia y misericordia en este momento?'
      ],
      prayerPrompt: 'Alaba a Dios por Su fidelidad. Pídele que te ayude a ver y celebrar las pequeñas y grandes muestras de Su gracia.'
    },
    {
      week: 6,
      title: 'CAPÍTULO 5: Necesitamos de otros',
      reading: 'Capítulo 5',
      centralIdea: 'Reconocer la necesidad de la comunidad y del apoyo de otros creyentes para caminar por el desierto sin desfallecer.',
      keyVerse: '“Dos son mejor que uno, porque tienen una buena recompensa por su trabajo. Porque si uno cae, el otro levanta a su compañero.” - Eclesiastés 4:9-10',
      reflectionQuestions: [
        '¿Quiénes son tus "dos" en este momento? ¿A quiénes has permitido que te acompañen en tu desierto?',
        '¿Te resulta difícil pedir ayuda o ser vulnerable? ¿Por qué?',
        '¿Cómo puedes ser un apoyo para otros en tu grupo de estudio?'
      ],
      prayerPrompt: 'Ora por tu grupo de estudio, pidiendo que Dios los fortalezca como comunidad y les dé la sabiduría para apoyarse mutuamente.'
    },
    {
      week: 7,
      title: 'CAPÍTULO 6: ¡No te escuches tanto!',
      reading: 'Capítulo 6',
      centralIdea: 'Aprender a someter nuestros pensamientos y emociones a la verdad de la Palabra de Dios en lugar de dejarnos llevar por ellos.',
      keyVerse: '“Porque las armas de nuestra milicia no son carnales, sino poderosas en Dios para la destrucción de fortalezas, derribando argumentos y toda altivez que se levanta contra el conocimiento de Dios, y llevando cautivo todo pensamiento a la obediencia a Cristo.” - 2 Corintios 10:4-5',
      reflectionQuestions: [
        '¿Qué "fortaleza" mental o patrón de pensamiento negativo necesitas derribar hoy?',
        '¿Cómo puedes llevar tus pensamientos cautivos a Cristo esta semana?',
        '¿Qué versículo bíblico puedes memorizar para combatir la mentira o el desánimo?'
      ],
      prayerPrompt: 'Pide a Dios que te dé el discernimiento para identificar las mentiras de Satanás y la fortaleza para someter tus pensamientos a la verdad.'
    },
    {
      week: 8,
      title: 'CAPÍTULO 7: Camina con Dios en el desierto',
      reading: 'Capítulo 7',
      centralIdea: 'Aceptar que el desierto es una temporada en la que Dios obra en nosotros, y que nuestro rol es caminar por fe, confiando en Su provisión.',
      keyVerse: '“Porque aguas serán cavadas en el desierto, y torrentes en la soledad.” - Isaías 35:6',
      reflectionQuestions: [
        '¿Qué significa para ti caminar con Dios en el desierto? ¿Cómo se ve eso en la práctica?',
        '¿Qué esperas que Dios haga por ti en el desierto? ¿Y qué esperas que Él haga en ti?',
        '¿Qué paso de obediencia puedes dar esta semana para caminar más cerca de Él?'
      ],
      prayerPrompt: 'Agradece a Dios por Su fidelidad y por la promesa de que Él estará contigo en cada paso de tu desierto.'
    },
    {
      week: 9,
      title: 'CAPÍTULO 8: Alimento en la aridez',
      reading: 'Capítulo 8',
      centralIdea: 'Descubrir que en el desierto, Dios nos provee de maneras inesperadas, especialmente a través del "maná" espiritual de Su Palabra y de Su Espíritu.',
      keyVerse: '“No solo de pan vivirá el hombre, sino de toda palabra que sale de la boca de Dios.” - Mateo 4:4',
      reflectionQuestions: [
        '¿Qué "maná" espiritual has recibido de Dios recientemente, ya sea a través de la Biblia, un sermón o un devocional?',
        '¿Cómo te ha sostenido Dios de manera inesperada en medio de tu aridez?',
        '¿Qué hábitos puedes crear para "alimentarte" regularmente de la Palabra de Dios?'
      ],
      prayerPrompt: 'Pide a Dios que te dé hambre por Su Palabra y te alimente espiritualmente en tu desierto.'
    },
    {
      week: 10,
      title: 'CAPÍTULO 9: No tendrás sed jamás',
      reading: 'Capítulo 9',
      centralIdea: 'Comprender que la meta no es salir del desierto, sino encontrar en Cristo la fuente inagotable de agua viva que nos satisface por completo.',
      keyVerse: '“Pero el que beba del agua que Yo le daré, no tendrá sed jamás.” - Juan 4:14',
      reflectionQuestions: [
        '¿Qué significa para ti la promesa de no tener sed jamás? ¿Cómo te consuela esto?',
        '¿En qué áreas de tu vida sigues buscando satisfacción fuera de Cristo?',
        '¿Qué puedes hacer esta semana para "beber" de Cristo y ser lleno de Su Espíritu?'
      ],
      prayerPrompt: 'Alaba a Dios por el don de Su Hijo, Jesucristo, la fuente de agua viva que satisface todas nuestras necesidades espirituales.'
    },
  ];

  const WelcomePage = () => (
    <div className="flex flex-col items-center justify-center p-8 text-center bg-white/70 rounded-lg shadow-xl animate-fade-in">
      <h2 className="text-3xl font-semibold text-rose-800 mb-4">Bienvenida al estudio de "Un Corazón en el Desierto"</h2>
      <p className="text-stone-600 mb-6 max-w-2xl">
        Esta aplicación ha sido diseñada para apoyar al primer grupo de lectura creado por el **Ministerio de Damas: Mujeres de Gracia**. Nuestro deseo es que esta herramienta te ayude a profundizar en cada capítulo y a abundar en el conocimiento de la Palabra de Dios. Que este tiempo juntas sea de gran bendición y crecimiento para cada una.
      </p>
      <button
        onClick={() => setView('study')}
        className="bg-rose-500 text-white px-6 py-3 rounded-lg shadow-md hover:bg-rose-600 transition-colors font-medium"
      >
        Empezar el Estudio
      </button>
    </div>
  );

  const StudyPage = () => {
    const currentStudy = studyData[currentWeek - 1];

    return (
      <div className="space-y-8 animate-fade-in">
        <div className="flex items-center justify-between p-4 bg-rose-200 rounded-lg font-bold text-rose-800">
          <button
            onClick={() => setCurrentWeek(prev => Math.max(1, prev - 1))}
            disabled={currentWeek === 1}
            className="p-2 rounded-full hover:bg-rose-300 disabled:opacity-50"
          >
            &#8592;
          </button>
          <span>Semana {currentWeek}: {currentStudy.title}</span>
          <button
            onClick={() => setCurrentWeek(prev => Math.min(studyData.length, prev + 1))}
            disabled={currentWeek === studyData.length}
            className="p-2 rounded-full hover:bg-rose-300 disabled:opacity-50"
          >
            &#8594;
          </button>
        </div>
        <div className="grid md:grid-cols-3 gap-6">
          <div className="md:col-span-2 bg-white/70 p-6 rounded-lg shadow-sm border border-rose-100">
            <h3 className="font-semibold text-xl text-stone-700 mb-3 flex items-center">
              <span className="mr-3 text-2xl">💡</span> Idea Central
            </h3>
            <p className="text-stone-600">{currentStudy.centralIdea}</p>
          </div>
          <div className="bg-white/70 p-6 rounded-lg shadow-sm border border-rose-100">
            <h3 className="font-semibold text-xl text-stone-700 mb-3 flex items-center">
              <span className="mr-3 text-2xl">📖</span> Versículo Clave
            </h3>
            <p className="text-stone-800 font-medium italic text-center text-lg">“{currentStudy.keyVerse.split(' - ')[0]}”</p>
          </div>
        </div>

        <div>
            <h3 className="font-semibold text-xl text-stone-700 mb-4 flex items-center">
              <span className="mr-3 text-2xl">🤔</span> Preguntas de Reflexión
            </h3>
            <div className="space-y-4">
              {currentStudy.reflectionQuestions.map((q, index) => (
                <div key={index} className="bg-white p-5 rounded-lg shadow-sm border border-rose-100 transition-shadow hover:shadow-md">
                  <p className="text-stone-700">{q}</p>
                </div>
              ))}
            </div>
        </div>

        <div className="bg-white p-6 rounded-lg shadow-sm border border-rose-100">
          <h3 className="font-semibold text-xl text-stone-700 mb-3">Notas Personales</h3>
          <textarea
            className="w-full h-40 p-3 bg-rose-50 rounded-md border border-rose-200 focus:ring-2 focus:ring-rose-300 focus:border-rose-300 transition"
            placeholder="Escribe tus notas para esta semana aquí..."
            value={notes}
            onChange={(e) => setNotes(e.target.value)}
          ></textarea>
        </div>
      </div>
    );
  };

  return (
    <div className="min-h-screen flex flex-col md:flex-row bg-rose-50 text-stone-800">
      <aside className="w-full md:w-64 bg-rose-100 p-6 shadow-lg md:min-h-screen">
        <h2 className="text-2xl font-bold text-rose-900 mb-6">Guía de Estudio</h2>
        <nav className="space-y-2">
          <a
            href="#"
            onClick={() => setView('home')}
            className={`block w-full text-left px-4 py-2 rounded-lg transition-colors hover:bg-rose-200 text-stone-700 ${view === 'home' && 'bg-rose-200 font-bold'}`}
          >
            Inicio
          </a>
          <a
            href="#"
            onClick={() => setView('study')}
            className={`block w-full text-left px-4 py-2 rounded-lg transition-colors hover:bg-rose-200 text-stone-700 ${view === 'study' && 'bg-rose-200 font-bold'}`}
          >
            Guía de Estudio
          </a>
        </nav>
      </aside>

      <main className="flex-1 p-6 md:p-10">
        <header className="mb-8">
          <h1 className="text-4xl md:text-5xl font-bold text-rose-800">Un Corazón en el Desierto</h1>
          <p className="text-lg text-stone-600 mt-2">Un viaje para encontrar ríos de agua viva en medio de la sequía espiritual.</p>
        </header>
        
        {view === 'home' && <WelcomePage />}
        {view === 'study' && <StudyPage />}
      </main>
    </div>
  );
};

export default App;
