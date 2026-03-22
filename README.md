# 🌱 BridgeClass — Tu Puente al Éxito

> **Bridging the educational gap for displaced students through AI-driven bilingual curriculum mapping and tutoring.**

BridgeClass is a bilingual web application designed to act as a personalized curriculum guide for displaced students and immigrants. By automatically translating and structuring foreign-language educational materials into a personalized, interactive roadmap, BridgeClass helps students seamlessly assimilate into new school systems without falling behind due to language barriers.

## ✨ Key Features

* **📄 Native Document Parsing:** Upload raw teacher notes, syllabi, or textbooks (PDF or TXT). BridgeClass uses client-side parsing to read the materials directly in the browser.
* **🗺️ Dynamic Curriculum Generation:** Powered by the Gemini API, the app analyzes foreign-language documents, translates the content into English, and structures it into an interactive UI roadmap.
* **🤖 BridgeBot (Bilingual AI Tutor):** An integrated, context-aware chatbot with memory. BridgeBot explains complex local concepts in the student's native language while teaching them the required academic vocabulary in their new target language.
* **📊 Personalized Dashboard:** Tracks unit progress, highlights active topics, and displays estimated starting mastery based on an initial diagnostic test.
* **⚡ Serverless & Fast:** Runs entirely on the client side using vanilla JavaScript and `localStorage`, bypassing the need for heavy backend infrastructure.

## 🛠️ Tech Stack

* **Frontend:** HTML5, CSS3, Vanilla JavaScript
* **AI & Logic:** [Google Gemini 2.5 Flash API](https://ai.google.dev/) (Curriculum mapping & BridgeBot conversational engine)
* **Libraries:** [PDF.js](https://mozilla.github.io/pdf.js/) (Client-side document parsing)
* **State Management:** Browser `localStorage`

## 🚀 How to Run Locally

Because BridgeClass relies on client-side rendering and external APIs, it is incredibly easy to run locally. No `npm install` or complex backend setup is required.

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/yourusername/bridgeclass.git](https://github.com/yourusername/bridgeclass.git)
    cd bridgeclass
    ```

2.  **Add your Gemini API Key:**
    * Open `app.html` in your favorite code editor.
    * Locate the API key constant (around line 520): 
        ```javascript
        const GEMINI_API_KEY = 'YOUR_API_KEY_HERE';
        ```
    * Replace `'YOUR_API_KEY_HERE'` with your actual Google Gemini API key.

3.  **Launch the App:**
    * Open `bridgeclass (1).html` (the diagnostic/landing page) in any modern web browser to start the user flow.
    * Alternatively, you can open `app.html` directly to view the main dashboard.

## 🧠 Technical Architecture & Overcoming Challenges

Building BridgeClass during a hackathon required some creative problem-solving:

* **The Formatting Friction:** When querying the Gemini API to act as our bilingual tutor, the AI generated responses using a mix of markdown and its own structural spacing. This clashed with our HTML containers, creating awkward whitespace. We built a custom JavaScript text-parsing pipeline to strip out conflicting HTML tags, compress newlines, and safely convert markdown into clean HTML for a sleek chat interface.
* **The Architecture Dilemma:** Due to tight hackathon constraints, building a robust backend database for user authentication and state management wasn't feasible. We pivoted to a localized solution, utilizing `localStorage` to pass session data between screens. We engineered a detailed default persona—"Marco Reyes," a student relocating from Canada to Mexico—allowing us to instantly demonstrate the platform's personalized features without a complex login flow.

## 🔮 What's Next?

* **Secure Backend Integration:** Implement Firebase or Supabase to handle user authentication, securely store uploaded curriculum documents, and retain ongoing chat histories across sessions and devices.
* **Expanded Language Support:** Scale the AI infrastructure to support a wider array of language pairs (e.g., Arabic to English, Ukrainian to German).
* **Voice-to-Text Capabilities:** Integrate audio features so students can practice speaking and pronunciation in their new academic language directly with BridgeBot.

## 🤝 Contributors

* [Your Name/GitHub Profile] - *Role/Contribution*
* [Teammate Name/GitHub Profile] - *Role/Contribution*

---
*Built with ❤️ for [Hackathon Name]*
