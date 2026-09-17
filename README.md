# olympic-blitz-arena
A real-time competitive speed-math platform for IMO prep.

 PROJECT PROPOSAL: COMPETITIVE MATH BLITZ
AN AGILE PROJECT BY TEAM OLYMPIA

1. Team Identity and Roles
- Team Olympia
- Team Roles and Assignments:
	· Project Manager: Setting up the Sprint Cycles, Tracking the Milestones and Key Metrics, Issuing Jira Tickets, Aggregating Question and Answer Data
	· Lead Backend Engineer: Determining the Optimal Answer Verification System, Designing the Multiplayer Session System and Matchmaking Algorithms (Elo), Work with Lead FEE on the Timer Integration Accounting for Slower Connections (Lag Compensation)
	· Lead Frontend Engineer: Designing an Efficient Input System, Timer Setup and Optimization, and the Question-Answer Layout
	· Database Admin: Set up the Database Format, Maintain Session Security and Login System with assistance from Lead BEE
	· DevOps Engineer: Automated Integration Pipeline Setup, Load-Test WebSocket Connections, Configure Automated Branch Protections
	· (Optional) Lead AI Developer: Integrate LLM System into the Lead FEE’s and Lead BEE’s game mechanics

2. Technology Stack and Frameworks
	· Backend Language and Framework: Java 21 with Spring Boot. Java is highly optimized for massive amounts of network connections, while maintaining security and avoiding extreme complexity/memory leaks, in a way that C++ simply is not.
	· Frontend Language and Framework: TypeScript with React for Efficient Cross-Platform Development.
	· Real-Time Protocol: WebSockets for Bidirectional Event Communication.
	· Database Management System: PostgreSQL for Relational data storage of the question banks and user profiles, with detailed user histories.

3. Challenge Statement and Solution
	· The Challenge: Traditional Standardized Test Prep is slow and uninteresting. It does not spark life into the student working on it. I very much enjoyed preparing for my tests, because I made a game out of it. I went head-to-head with my very own self, and I did so under the rigorous time controls of the actual exam itself, which requires a lot of speed. I took three practice tests, and I graded myself on each one. I felt great when I did well, and I felt angry with myself when I saw stupid errors. This is exactly the kind of competitive nature that is evoked by modern video games, making children practice them for HOURS without being told, but no test prep solution as of yet has managed to take advantage of their competitive nature.
	· The Solution: The student shall go head-to-head against others in a battle of the wits. It shall evoke the same imagery as Clash Royale or Chess.com, two extremely popular games that children play for fun. We will make the student unable to move on to the next battle without understanding what he (or she) got wrong previously. We will implement Large Language Models into the one-time analysis of each problem and each possible mistake. Thus we shall meet our goal of enforcing understanding and developing creative linguistic methods of ensuring that our patient has been cured of his (or her) lack of knowledge. He (or she) will need to state what exactly the mistake was that was made in order to move on to fighting the next opponent and potentially getting that Elo back! This is how we will train the next generation of geniuses!

4. Geoffrey Moore Template:
	· FOR (target customer): ambitious students, competitive math enthusiasts, gamers, and anyone who loves to learn (by which I do mean everyone)
	· WHO (statement of the need or opportunity) need an outlet for their competitive drive that will build up their skills and knowledge in the world, rather than pigeon-holing them into the locked-in rules of a video game
	· The (PRODUCT NAME) Olympia Blitz Arena
is a (product category) real-time competitive science platform
	· THAT (key benefit, compelling reason to buy) combines deep, fun and engaging problems with aggressive time pressure and serious competition
	· UNLIKE (primary competitive alternative) flashcards and boring, anti-motivational practice quizzes
	· OUR PRODUCT (statement of primary differentiation) gamifies the act of learning by making students HATE being bad at science and school!

5. Risk Management Plan:
- Risk Identification and Analysis
	· Network Latency Disadvantages: Players with slower connections could be punished if our Lead BEE and FEE fail to account for
	· Concurrency Overload: Distributing the System properly to allow for many active lobbies is an important back-end engineering job, for both the Lead BEE and the Dev/Ops Engineer.
	· XSS and Other Input Exploits: Automated Solvers and other kinds of Cheaters are a huge issue in game development.
- Risk Mitigation Strategies
	· Chess.com has implemented significant Lag Compensation methods, but I have found that LiChess’ practices are better for that and result in fairer bullet time controls. I do still enjoy chess.com’s community, but this improvement along with the fact that LiChess’ codebase is open source enables me to significantly improve my own product’s Lag Compensation and Match-Making by basing it off of LiChess’, as well as by routing players more consistently to closer opponents on the Internet map. Fortunately, we do not have to deal with the presence of chess’ alternating move sequencing problem, with the clocks pausing when a player makes his or her move. This simplifies things greatly. Emphasis on having one unified clock (and being reminded of your opponent’s answer rate) will be very useful here.
	· Lightweight Server Setup: Java’s virtual threads will enable us to keep the game itself stateless on the server.
	· Obfuscated Asset Delivery: If we can render our questions using images, then the users will not be able to write scripts that immediately query LLMs to answer them without slow Optical Character Recognition algorithms that would give the edge back to a real student.
- Risk Tracking
	· Monitor active connection ping times in daily automated internal test matches
	· Utilize automated load-testing frameworks to simulate massive concurrent lobbies before deploying to production
