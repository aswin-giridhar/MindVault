# 🧠 MindVault - Private AI Journal

<p align="center">
  <img src="mindvault_logo.png" alt="MindVault Logo" width="120" />
</p>

> **Your memories, secured locally. AI that never leaves your device.**

MindVault is a privacy-first AI journal that runs **100% on-device** using the Cactus SDK. Capture thoughts via voice, image or text, get AI-powered mood analysis and summaries, search memories semantically, and chat with an intelligent assistant that understands your journal history—all without any data ever leaving your phone.

---

## 🏆 Hackathon Tracks

| Track | Name | Our Implementation |
|-------|------|-------------------|
| **Main Track** | Best Mobile Application with On-Device AI | ✅ Complete journaling app with 5+ AI features |
| **Track 1** | Memory Master | ✅ Shared memory/knowledge base with RAG chat |
| **Track 2** | Hybrid Hero | ✅ Smart local ↔ cloud fallback router |

---

## 🚀 Quick Start: Run the APK

### APK File

| File | Description |
|------|-------------|
| **MindVault.apk** | Production build - ready to install! |

### 🎬 Demo Video

| File | Description |
|------|-------------|
| **MindVault.mp4** | 1-minute demo showcasing all AI features |

> Watch the demo to see voice transcription, mood analysis, and Memory Master chat in action!

> **⚠️ Important:** This app uses the Cactus SDK with native ARM libraries. **Test on a real Android phone** (not emulators like BlueStacks which use x86 architecture).

### 📋 Device Requirements

| Requirement | Minimum | Recommended |
|-------------|---------|-------------|
| **Android Version** | Android 7.0 (API 24) | Android 10+ |
| **Architecture** | ARM64 (64-bit) | ARM64 |
| **Storage** | 500MB free | 1GB+ free |
| **RAM** | 4GB | 6GB+ |

> **Note:** x86/x86_64 emulators (BlueStacks, Android Studio Emulator) are **NOT supported** due to ARM-only native libraries.

### Installation Steps
1. Download `MindVault.apk` from the repository
2. Transfer to your Android device (USB, Google Drive, email, etc.)
3. On Android: **Settings → Security → Enable "Install from Unknown Sources"**
4. Tap the APK file to install
5. Open **MindVault** and grant permissions when prompted:
   - 🎤 Microphone (for voice recording)
   - 📷 Camera (for photo entries)
   - 📍 Location (for weather context)

### First Launch
- Models will auto-download (~500MB total) on first use
- Works **completely offline** after initial model download
- No account needed, no sign-up required

---

## 🛠 Tech Stack

| Component | Technology |
|-----------|------------|
| **Framework** | React Native 0.82 |
| **AI Runtime** | [Cactus SDK](https://github.com/cactus-ai/cactus-react-native) |
| **Language** | TypeScript |
| **Storage** | AsyncStorage (on-device) |
| **Platform** | Android (APK) |

---

## 🤖 AI Models Used

All models run **locally on-device** via the Cactus SDK:

| Model | Capability | Usage in App |
|-------|------------|--------------|
| **whisper-small** | Speech-to-Text | Voice transcription |
| **qwen3-0.6b** | Text LLM | Mood analysis, summaries, chat, prompts |
| **lfm2-vl-450m** | Vision-Language | Photo understanding & descriptions |
| **mxbai-embed-2k** | Embeddings | Semantic search across journal entries |

---

## ✨ AI Capabilities

### 1. 🎤 Speech-to-Text (STT)
- Real-time voice transcription using Whisper
- Works offline, zero latency
- Distinguishes between typed vs. transcribed text

### 2. 🧠 AI Analysis & Reasoning
- **Mood Detection**: Analyzes text to determine emotional state (happy, sad, anxious, etc.)
- **Smart Summaries**: Generates concise 1-sentence summaries of entries
- **AI Journaling Prompts**: Generates personalized prompts to inspire reflection

### 3. 📷 Vision-Language (Photo AI)
- Understands and describes photos added to journal entries
- "A sunset over the ocean with silhouettes of palm trees"
- Integrates description into entry for AI context

### 4. 🔍 RAG (Retrieval-Augmented Generation)
- Embed all journal entries as vectors
- Semantic search: Find entries by *meaning*, not just keywords
- Chat assistant uses relevant entries as context (source grounding)

### 5. 🔧 Tool Calling
| Tool | Function |
|------|----------|
| `search_entries` | Find specific journal entries |
| `get_mood_summary` | Analyze mood trends over time |
| `create_reminder` | Set journaling reminders |

### 6. ☁️ Smart Cloud Fallback Router
- **Default**: All AI runs locally (100% private)
- **Optional Toggle**: Enable cloud fallback via Google Gemini API
- **Router Pattern**: Try local first → fall back to cloud if needed
- Toggle in Profile screen: "Enable Cloud AI"

---

## 📱 App Screens

### 1. Timeline (Home)
- View all journal entries chronologically
- Filter by mood (😊 Happy, 😢 Sad, 😰 Anxious, etc.)
- Semantic search with AI embeddings
- Weather displayed on each entry
- Audio playback for voice entries
- Photo thumbnails

### 2. Record (New Entry)
- AI-generated journaling prompts
- Voice recording → automatic transcription
- Photo capture with AI description
- Mixed typing + voice + photos
- Weather badge auto-capture

### 3. Entry Detail
- Full entry view with segments
- Photo + AI description display
- Audio playback
- Weather info
- Mood emoji

### 4. Memory Master (Chat)
- Chat with AI about your journal history
- RAG-powered: AI references actual entries
- Source grounding: Clickable links to original entries
- Quick actions: 📊 Week Mood, 🔍 Search, ⏰ Remind
- Shows Local vs Cloud badge on responses

### 5. Profile (Insights)
- Journaling streak tracker
- Weekly activity chart
- Mood statistics with bar chart
- Filtering: 7d / 30d / 90d / All time
- Daily AI motivation quotes
- Cloud toggle switch

---

## 🔒 Edge Capabilities

### Total Privacy
- ✅ All AI inference runs on-device
- ✅ No data sent to servers (unless cloud toggle enabled)
- ✅ No accounts, no tracking, no analytics
- ✅ Entries stored only in local AsyncStorage
- ✅ Audio files stored locally, never uploaded

### Zero Latency
- ✅ Instant transcription (no network round-trip)
- ✅ Real-time mood analysis
- ✅ Immediate response from chat assistant
- ✅ Fast semantic search

### Offline Capability
- ✅ Works in airplane mode
- ✅ No internet required after initial model download
- ✅ All features functional offline
- ✅ Local storage persists across sessions

---

## 📊 Evaluation Criteria Mapping

### 1. Technical Implementation
| Requirement | Implementation |
|-------------|----------------|
| Deep Cactus SDK integration | ✅ 4 models: STT, LLM, Vision, Embeddings |
| Local inference | ✅ All AI runs on-device |
| Not just API wrapper | ✅ Full native app with complex features |

### 2. Edge Capabilities
| Requirement | Implementation |
|-------------|----------------|
| Offline Capability | ✅ Works without internet |
| Zero Latency | ✅ Real-time STT + instant AI |
| Total Privacy | ✅ No data leaves device |

### 3. Design & UX 
| Requirement | Implementation |
|-------------|----------------|
| Polished interface | ✅ Consistent dark theme across 5 screens |
| Intuitive UX | ✅ Simple voice/text entry flow |
| Fluid responsiveness | ✅ Loading states, progress indicators |
| Mobile-first | ✅ Native React Native app |

### 4. Utility & Innovation 
| Requirement | Implementation |
|-------------|----------------|
| Solves real problem | ✅ Private journaling with AI insights |
| Beyond chat interface | ✅ Voice journal, mood tracking, semantic search, photo AI |
| Novel functionality | ✅ RAG-powered memory assistant, vision understanding |

### 5. Completeness 
| Requirement | Implementation |
|-------------|----------------|
| Functional build | ✅ Working Android APK |
| Testable | ✅ All features functional |
| By deadline | ✅ Submitted |

---

## 📁 Repository Structure

```
VoiceJournal/
├── App.tsx                 # Navigation setup
├── src/
│   ├── screens/
│   │   ├── TimelineScreen.tsx    # Home with entries list
│   │   ├── RecordScreen.tsx      # Create new entry
│   │   ├── EntryDetailScreen.tsx # View entry
│   │   ├── ChatScreen.tsx        # Memory Master
│   │   └── ProfileScreen.tsx     # Insights & settings
│   ├── services/
│   │   ├── AIAnalysis.ts         # Mood/summary analysis
│   │   ├── AudioRecording.ts     # Voice recording
│   │   ├── CloudService.ts       # Cloud fallback router
│   │   ├── EmbeddingService.ts   # Vector embeddings
│   │   └── WeatherService.ts     # Weather API
│   ├── utils/
│   │   └── storage.ts            # AsyncStorage wrapper
│   └── types/
│       └── index.ts              # TypeScript interfaces
├── android/                      # Android native code
└── package.json
```

---

## 🌐 Hybrid Cloud Strategy

MindVault implements the **Hybrid Hero** pattern:

### How to Enable Cloud Fallback (For Judges):
1. **Open the app** → You start on the **Timeline** (home screen)
2. **Tap the 👤 Profile icon** in the bottom navigation bar (right side)
3. **Scroll down** to the "Settings" section
4. **Find "☁️ Enable Cloud AI"** toggle switch
5. **Tap to enable** → Toggle turns ON (green)
6. Go to **Memory Master (💬 Chat)** and ask a question
7. **Look for the badge** on AI responses: `📱 Local` or `☁️ Cloud`

### Router Pattern Diagram:

```
┌─────────────────────────────────────────────────┐
│                 User Input                      │
└─────────────────────┬───────────────────────────┘
                      │
                      ▼
┌─────────────────────────────────────────────────┐
│      Cloud Enabled Toggle? (Profile Screen)     │
│      👤 → Scroll → "Enable Cloud AI" toggle    │ 
└─────────────────────┬───────────────────────────┘
                      │
          ┌───────────┴───────────┐
          │ OFF                   │ ON
          ▼                       ▼
┌─────────────────┐    ┌─────────────────────────┐
│   LOCAL ONLY    │    │   TRY LOCAL FIRST       │
│   (Cactus SDK)  │    │   ↓                     │
│   100% Private  │    │   If fails → Cloud      │
└─────────────────┘    │   (Google Gemini API)   │
                       └─────────────────────────┘
```

### How to See Which AI Responded:
In the **Memory Master (💬 Chat)** screen, each AI response shows a badge:
- **`📱 Local`** = Response from on-device Cactus SDK (100% private)
- **`☁️ Cloud`** = Response from Google Gemini cloud API

This makes it transparent which AI answered your question!

---

## 🎬 Demo Flow

1. **Open app** → See empty timeline with prompt to create first entry
2. **Tap + button** → Record screen with AI-generated prompt
3. **Record voice** → Speak thoughts → See real-time transcription
4. **Add photo** → AI describes image content
5. **Save** → AI analyzes mood + generates summary
6. **View timeline** → Entry appears with mood emoji and weather information at the time of entry
7. **Search** → Type query → Semantic search finds related entries
8. **Chat** → Ask "What made me happy last week?" → AI responds with sources
9. **Profile** → See mood trends, journaling streak, toggle cloud

---

## 👨‍💻 Team

Built with ❤️ during the Cactus x Nothing x Hugging Face Hackathon, November 2025. 

[Aswin Giridhar](https://www.linkedin.com/in/aswin-giridhar-subramanian/)

---

## 📝 License

MIT License - Feel free to learn from this code!

---

<p align="center">
  <b>MindVault</b> - Your memories. Your device. Your privacy. 🔐
</p>
