# Blues Fuel Coach 🥜⚾

Nutrition chatbot for the Blues 10U select baseball team. Helps players and parents learn about game-day nutrition, hydration, healthy snacks, and how food fuels performance.

## Stack

- **Frontend**: Static HTML/CSS/JS — no framework, just a clean chat interface
- **Backend**: Vercel serverless function (`/api/chat`) → Anthropic API (Claude)
- **Hosting**: Vercel free tier

## Setup

1. Clone this repo
2. Install dependencies: `npm install`
3. Create a `.env.local` file with your Anthropic API key:
   ```
   ANTHROPIC_API_KEY=sk-ant-...
   ```
4. Run locally: `npx vercel dev`
5. Deploy: `npx vercel --prod`

## Environment Variables

| Variable | Description |
|----------|-------------|
| `ANTHROPIC_API_KEY` | Your Anthropic API key. Set in Vercel dashboard under Settings → Environment Variables. |

## Model

Uses `claude-sonnet-4-20250514` by default. To switch to a cheaper/faster model, edit the `MODEL` constant in `api/chat.js` (e.g., `claude-3-5-haiku-20241022`).

## Cost

Uses `gpt-4o-mini` — extremely cheap. A team of 12 families chatting casually will run well under $1/month.

## Guardrails

- No supplement recommendations for children
- Redirects medical/allergy questions to professionals
- No weight loss advice for kids
- No calorie counting
- Positive framing around all food choices
- Energy drinks are a hard no
