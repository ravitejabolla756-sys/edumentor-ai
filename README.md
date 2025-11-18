# 🎓 EduMentor AI

> AI-powered educational assistant agent for personalized learning

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![Kaggle](https://img.shields.io/badge/Kaggle-Capstone-20BEFF?logo=kaggle)](https://www.kaggle.com/competitions/agents-intensive-capstone-project)

## 📋 Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Architecture](#architecture)
- [Course Concepts](#course-concepts)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Evaluation](#evaluation)
- [Contributing](#contributing)
- [License](#license)

## 🌟 Overview

EduMentor AI is an intelligent educational assistant built for the **Kaggle AI Agents Intensive Capstone Project** (Agents for Good track). It provides personalized learning support to students through:

- 🤖 Adaptive tutoring with intelligent question generation
- 📚 Interactive study material recommendations
- ✅ Practice problem generation and evaluation
- 📊 Learning progress tracking and insights
- 🧠 Memory-enabled conversations for context-aware assistance

**Mission**: Make quality education accessible to all students by providing 24/7 personalized AI tutoring.

## ✨ Features

### Core Capabilities
- **Multi-Agent System**: Specialized agents for tutoring, content generation, and assessment
- **Custom Tools**: Search, calculator, code execution, and study resource tools
- **Session Memory**: Remembers student progress and preferences across conversations
- **Observability**: Full logging and monitoring with LangSmith integration
- **Agent Evaluation**: Automated testing and quality metrics

### Student-Focused Benefits
- Personalized learning paths based on student's level and pace
- Instant explanations for complex topics
- Practice problems with step-by-step solutions
- Study planning and time management guidance
- Multi-subject support (Math, Science, Programming, etc.)

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────┐
│                    EduMentor AI                         │
│                  (Orchestrator Agent)                   │
└───────────────────┬─────────────────────────────────────┘
                    │
        ┌───────────┴──────────┬──────────────┐
        │                      │              │
        ▼                      ▼              ▼
┌───────────────┐    ┌───────────────┐  ┌──────────────┐
│  Tutor Agent  │    │ Content Agent │  │ Quiz Agent   │
│   (Teaching)  │    │  (Resources)  │  │(Assessment)  │
└───────┬───────┘    └───────┬───────┘  └──────┬───────┘
        │                    │                  │
        └────────────────────┴──────────────────┘
                             │
                    ┌────────▼─────────┐
                    │   Custom Tools   │
                    │ ─ Search Engine  │
                    │ ─ Calculator     │
                    │ ─ Code Runner    │
                    │ ─ Study Tracker  │
                    └──────────────────┘
```

## 📖 Course Concepts Implemented

This project demonstrates **5+ concepts** from the 5-Day AI Agents Intensive:

1. **✅ Multi-Agent Systems** (Day 1b)
   - Orchestrator coordinates specialized tutor, content, and quiz agents
   - Agent-to-Agent communication using A2A protocol

2. **✅ Custom Tools & MCP** (Day 2a, 2b)
   - Search tool for finding study resources
   - Calculator for math problems
   - Code execution tool for programming help
   - Study progress tracker

3. **✅ Session & Memory Management** (Day 3a, 3b)
   - Persistent student profiles
   - Conversation history across sessions
   - Learning progress tracking

4. **✅ Agent Observability** (Day 4a)
   - LangSmith integration for monitoring
   - Detailed logging of agent decisions
   - Performance metrics tracking

5. **✅ Agent Evaluation** (Day 4b)
   - Automated test cases for agent responses
   - Quality metrics (accuracy, helpfulness)
   - User feedback integration

6. **✅ A2A Protocol** (Day 5a)
   - Agents communicate via standardized messages
   - Task delegation between specialized agents

## 🚀 Installation

### Prerequisites
- Python 3.10 or higher
- Google AI API key ([Get one here](https://makersuite.google.com/app/apikey))
- Git

### Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/ravitejabolla756-sys/edumentor-ai.git
   cd edumentor-ai
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Set up environment variables**
   ```bash
   cp .env.example .env
   # Edit .env and add your GOOGLE_API_KEY
   ```

4. **Run the application**
   ```bash
   python main.py
   ```

## 💻 Usage

### Quick Start

```python
from edumentor import EduMentorAI

# Initialize the agent
mentor = EduMentorAI(api_key="your_google_api_key")

# Start a tutoring session
response = mentor.chat(
    student_id="student123",
    message="Can you help me understand quadratic equations?"
)

print(response)
```

### Example Interactions

**1. Learning New Concepts**
```
Student: "Explain photosynthesis in simple terms"
EduMentor: "Photosynthesis is how plants make food using sunlight..."
```

**2. Practice Problems**
```
Student: "Give me a practice problem on algebra"
EduMentor: "Solve for x: 2x + 5 = 15. I'll guide you step by step..."
```

**3. Study Planning**
```
Student: "Help me prepare for my physics exam next week"
EduMentor: "Let's create a study plan covering all key topics..."
```

## 📁 Project Structure

```
edumentor-ai/
├── agents/                 # Agent implementations
│   ├── orchestrator.py    # Main coordinator agent
│   ├── tutor_agent.py     # Teaching specialist
│   ├── content_agent.py   # Resource finder
│   └── quiz_agent.py      # Assessment creator
├── tools/                  # Custom tool implementations
│   ├── search_tool.py
│   ├── calculator.py
│   ├── code_runner.py
│   └── study_tracker.py
├── memory/                 # Session and memory management
│   ├── session_store.py
│   └── student_profile.py
├── evaluation/             # Testing and metrics
│   ├── test_cases.py
│   └── metrics.py
├── main.py                 # Application entry point
├── requirements.txt        # Python dependencies
├── README.md              # This file
├── LICENSE                # MIT License
└── .env.example           # Environment template
```

## 📊 Evaluation

The agent is evaluated on:

- **Accuracy**: Correctness of educational content
- **Helpfulness**: Quality of explanations and guidance
- **Responsiveness**: Speed and relevance of responses
- **User Satisfaction**: Student feedback scores

Run evaluation suite:
```bash
python -m evaluation.run_tests
```

## 🤝 Contributing

Contributions are welcome! Please:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🏆 Kaggle Competition

This project is submitted to:
- **Competition**: [AI Agents Intensive - Capstone Project](https://www.kaggle.com/competitions/agents-intensive-capstone-project)
- **Track**: Agents for Good (Education)
- **Submission Date**: November 2025

## 👤 Author

**Ravi Teja Bolla**
- GitHub: [@ravitejabolla756-sys](https://github.com/ravitejabolla756-sys)
- Email: ravitejabolla756@gmail.com
- LinkedIn: [Connect with me](https://linkedin.com/in/ravitejabolla)

## 🙏 Acknowledgments

- Google for the Gemini API and 5-Day AI Agents Intensive Course
- Kaggle for hosting the capstone competition
- The open-source AI community

---

**Made with ❤️ for students everywhere**
