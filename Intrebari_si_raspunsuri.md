# Întrebări și Răspunsuri

### Ce este un viewport?
Un viewport este o regiune a ferestrei de desen în care OpenGL va desena conținutul grafic. Practic, viewport-ul definește dimensiunea și poziția zonei de afișare în fereastra aplicației. În OpenGL, `GL.Viewport` este utilizat pentru a seta această regiune.

### Ce reprezintă conceptul de frames per seconds (FPS) din punctul de vedere al bibliotecii OpenGL?
FPS măsoară câte cadre sunt randate și afișate pe ecran într-o secundă. În OpenGL, FPS-ul indică frecvența cu care metoda `RenderFrame` este apelată pentru a desena o scenă nouă. Cu cât FPS-ul este mai mare, cu atât animațiile vor părea mai fluide.

### Când este rulată metoda `OnUpdateFrame()`?
`OnUpdateFrame()` este apelată înainte de fiecare randare a unui cadru și este utilizată pentru a actualiza logica jocului sau a aplicației, cum ar fi calcularea mișcărilor obiectelor sau actualizarea stării aplicației.

### Ce este modul imediat de randare?
Modul imediat de randare (Immediate Mode) este un mod vechi de randare în OpenGL, unde comenzile de desen sunt transmise direct în pipeline-ul grafic folosind funcții precum `glBegin()` și `glEnd()`. Acest mod este considerat ineficient pentru că fiecare apel trimite date direct către GPU.

### Care este ultima versiune de OpenGL care acceptă modul imediat?
Modul imediat este suportat până la OpenGL 3.0, dar în versiunile ulterioare, acest mod a fost deprecate în favoarea modurilor mai eficiente, cum ar fi VBO (Vertex Buffer Objects) și VAO (Vertex Array Objects).

### Când este rulată metoda `OnRenderFrame()`?
`OnRenderFrame()` este apelată de fiecare dată când un cadru nou trebuie să fie desenat. Acest lucru se întâmplă la o frecvență specificată (de exemplu, 60 FPS), și aici are loc desenarea efectivă a scenei.

### De ce este nevoie ca metoda `OnResize()` să fie executată cel puțin o dată?
`OnResize()` este apelată atunci când fereastra este redimensionată, iar setările pentru viewport și proiecție trebuie recalibrate pentru noile dimensiuni ale ferestrei. Aceasta asigură că obiectele sunt afișate corect în funcție de dimensiunile actualizate.

### Ce reprezintă parametrii metodei `CreatePerspectiveFieldOfView()` și care este domeniul de valori pentru aceștia?
`CreatePerspectiveFieldOfView()` creează o matrice de proiecție de tip perspectivă, iar parametrii săi sunt:

- **fovY**: unghiul de vedere pe axa verticală (în radiani). Domeniul tipic este între 30 și 90 de grade.
- **aspectRatio**: raportul dintre lățime și înălțime al viewport-ului.
- **zNear**: distanța față de planul apropiat de clipping.
- **zFar**: distanța față de planul îndepărtat de clipping.

Valorile pentru acești parametri depind de nevoile aplicației, însă un domeniu obișnuit pentru `fovY` este [30, 90] de grade.
