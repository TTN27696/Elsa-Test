# Elsa-Test
My submission for Elsa Test  
1.Architecture Diagram  
![Real-Time Quiz Architecture](https://raw.githubusercontent.com/TTN27696/Elsa-Test/main/RealTimeQuiz.png)  

2.Component Descriptions  
- View: Enter a quiz id, open real time quiz feature, show questions, score, leaderboard.
- View Model: Acts as a bridge between View and domain logic. It exposes UI state, handles user actions (e.g., join quiz, submit answer), and invokes corresponding use cases.
- Use Cases: Encapsulate business logic (e.g., JoinQuizUseCase, SubmitAnswerUseCase, ObserveLeaderboardUseCase). They help isolate logic from UI and make the code testable and reusable.
- Repository: It communicates with REST API and WebSocket services to get/send quiz data, answers, scores, and leaderboard updates.
- Quiz API & WebSocket Server: Backend services that handle quiz sessions, scoring logic, and real-time data delivery through WebSocket for scores and leaderboard updates.

3.Data Flows
- Step 1: Users enter quiz id and press "Start".
- Step 2: View Model triggers JoinQuizUseCase.
- Step 3: Use case calls Repository to interact with Quiz API.
- Step 4: If response is successful, quiz datas are returned and shown on the view.
- Step 5: When the users submit an answer, a similar flow happens via SubmitAnswerUseCase.
- Step 6: Real-time updates (scores/leaderboard) come in through WebSocket and are emitted by the Repository.
- Step 7: ViewModel updates the state and the UI reflects changes instantly.

4.Technology Justification
- UI: Jetpack Compose / XML Layouts - Native Android UI
- Logic: ViewModel + Kotlin Coroutines - Lifecycle-safe & responsive
- Data: Repository pattern - Scalable architecture
- Real-Time Updates: WebSockets (okhttp) - Bi-directional communication
- REST API: Retrofit - HTTP APIs (join quiz, submit answers)
- Data Sync: StateFlow/SharedFlow - Real-time UI updates

5. My Recording

📽️ [Watch the video presentation](https://drive.google.com/file/d/1RUo7p_tKiiBtbntXJYpAxB_TJ2fB1PTd/view?usp=sharing)
