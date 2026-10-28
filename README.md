# RunTimeError Hackathon

🔐 Bayora Blind Arena
Securing Adversarial AI Safety Testing Infrastructure
Hack in Hills --- Powered by TinyFish | Problem Statement 4
Team: RunTimeError

Bayora Blind Arena is a privacy-focused infrastructure for adversarial
AI safety testing. It aims to protect sensitive information, isolate
testing components, and provide verifiable evidence of test integrity.
Problem Statement
Adversarial AI testing involves Red Teams attempting to exploit AI
models while Blue Teams defend them. When these components share
resources, risks can include sensitive payload leakage, exposure of
defence strategies, side-channel information leakage, and tampered audit
records.
Our Solution
Bayora Blind Arena creates a controlled testing environment where
interactions pass through a centralized Policy Gateway.
Key Features
- Centralized Policy Gateway: Controls interactions between the
  Red Team, Blue Team, and the AI model.
- Sealed Defence Module: Uses WebAssembly to keep internal defence
  policies hidden while returning verdicts.
- Commit-Reveal Mechanism: Helps verify that testing commitments
  remain consistent throughout a session.
- Side-Channel Mitigation: Uses cache isolation and timing
  normalization to reduce information leakage.
- Tamper-Evident Audit Trail: Uses SHA-256 hash chaining and
  Ed25519 digital signatures to support integrity verification.
- Canary Auditor: Checks monitored surfaces for potential secret
  leakage.
- Integrity Certificate: Provides verifiable evidence of a
  session's recorded integrity.
How It Works
1. The Red Team submits adversarial prompts and attack attempts.
2. The Policy Gateway controls interactions within the testing
   workflow.
3. The Blue Team's defence module returns verdicts without exposing
   its internal policies.
4. The AI model under test processes requests through the
   controlled workflow.
5. Audit and monitoring components record relevant events and check for
   potential leakage.
6. An integrity certificate is generated at the end of a session.
Tech Stack
- Backend: FastAPI
- AI Model Runtime: Ollama
- Defence Isolation: WebAssembly
- Containerization: Docker Compose
- Database and Audit Storage: SQLite
- Frontend: Project-specific frontend interface
Experimental Results
In our simulated timing experiment, attacker classification accuracy
decreased from 95% to 52.5% with timing normalization enabled.

This approaches the 50% random-guessing baseline for balanced binary
classification. These results are specific to the simulated experiment
and do not establish protection against every possible side-channel
attack.
Target Users
- AI research laboratories and model providers
- Enterprises deploying large language models
- Independent AI safety and security auditors
Future Scope
- Stronger isolation using microvirtual machines
- Hardware-backed signing and remote attestation
- Additional adversarial testing benchmarks
- Integration with automated CI/CD security pipelines
- Expanded side-channel evaluation and performance testing
Team RunTimeError
- Dhritika Kashyap --- Team Leader
- Prem Jadhav --- Team Member
- Kamya Arora --- Team Member
Disclaimer
Bayora Blind Arena is a hackathon-stage prototype. Its security
mechanisms aim to reduce specific risks but do not guarantee complete
isolation or eliminate every vulnerability.
