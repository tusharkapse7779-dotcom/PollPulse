# PollPulse
PollPulse – AI-powered election guide with interactive heatmap, EVM simulator, voice assistant, and voter services. Built for Google Antigravity hackathon.
# PollPulse – Interactive Election Guide & Voting Simulator

**Google Antigravity Hackathon Submission**  
**Vertical: Election Guide & Voter Assistant**

---

## 🧭 Approach & Logic

PollPulse is a comprehensive, AI-powered election companion that guides voters through the entire electoral journey — from registration to results. The logic is built around a **Voter Journey** (6 steps) mapped to dedicated views:

1. **Register to Vote** – AI-assisted form with validation
2. **Find Your Booth** – Interactive map with heat layer and markers
3. **Required Documents** – Links to Election Commission forms
4. **EVM Practice** – Realistic ballot machine with sound
5. **Cast Vote (Booth)** – Candidate selection with VVPAT simulation
6. **Check Results** – Dynamic coalition projection charts

Dynamic data (seat counts) flows through all views: voting updates the dashboard and charts in real time. The assistant adapts to language (EN/HI/MR) and offers voice control via Google Speech Recognition.

---

## ⚙️ How the Solution Works

- **Sidebar Navigation** – Seamless switching between views, each with its own state.
- **AI Assistant** – Floating chat widget answers voter queries (rule-based, extensible).
- **Voice Commands** – "map", "services", "mps" – triggers view switches, works offline with speech synthesis fallback.
- **Interactive Map** – Leaflet.js with `leaflet.heat` plugin toggles a heatmap intensity layer over 6 predefined booths. Markers show queue/wait time.
- **EVM & Voting Booth** – Simulated beep, blinking lamp, candidate selection with VVPAT slip.
- **Dashboard** – Doughnut & bar charts (Chart.js) for coalition projection, plus a compact map.
- **Voter Services & MPS/MLA** – Direct links to official ECI forms and government profiles.
- **Offline / PWA** – Service worker caches critical assets; installable with manifest.

---

## 🔧 Google Services Integration

| Google Service | How It's Used |
|----------------|----------------|
| **Google Fonts** | Inter font (loaded from Google Fonts CDN) |
| **Google Speech Recognition** | Web Speech API (voice commands) – Chrome/Edge |
| **Google Sheets (mocked)** | Simulated live turnout fetch with deterministic update |
| **Google Maps (indirect)** | Leaflet basemap (CartoDB) – alternative when Maps API not available |

*Note:* The map uses CartoDB tiles (OpenStreetMap) as a direct Google Maps API could require billing. The architecture easily swaps to Google Maps if needed.

---

## 🧪 Testing & Validation

- **EVM Vote Logic** – Tested by repeated voting; seat totals never exceed 543.
- **Booth Vote Flow** – Candidate selection, disabled button until chosen, VVPAT print and auto‑reset.
- **Voice Commands** – Tested with "map", "services", "mps", "booth" – console logs command for debug.
- **Responsive Design** – Media queries collapse sidebar, stack stats on mobile.
- **Accessibility** – Skip link, `aria-live` log, `prefers-reduced-motion` support, focus‑visible outlines, proper semantic HTML.
- **Offline** – Service worker caches core resources; tested with Lighthouse.

---

## ♿ Accessibility

- Skip-to-content link
- Keyboard navigable (tabindex, focus styles)
- ARIA live region for status messages
- Reduced motion media query
- Language selection (EN, हिंदी, मराठी)
- High contrast UI (dark theme)

---

## 📝 Assumptions

- Browser supports Web Speech API for voice (falls back gracefully).
- Leaflet.heat plugin is loaded from CDN (cdnjs). No offline heatmap needed.
- Mock turnout data simulates Google Sheets; real integration would require a Google Apps Script endpoint.
- The map data is demo (Delhi booths); real booth data could be fetched from ECI API.

---

## 🚀 Run Locally

Just open `index.html` in a modern browser. For full PWA offline experience, serve via a local server (e.g., `npx serve`).

---

**Built with ❤️ for Indian voters.**
#BuildwithAI #PromptWarsVirtual

 @googlefordevelopers
 @hack2skill
