# CLAUDE.md

TLDW (Too Long; Didn't Watch) is a Next.js 15 app that transforms YouTube videos into AI-generated highlight reels using Gemini, with Supabase for auth and storage.

## Key Commands

```bash
npm run dev      # Dev server (Turbopack)
npm run build    # Production build (Turbopack)
npm run lint     # ESLint
```

## Environment Variables

Required in `.env.local`:
- `GEMINI_API_KEY` — Google Gemini API key
- `SUPADATA_API_KEY` — Supadata transcript API key
- `NEXT_PUBLIC_SUPABASE_URL` — Supabase project URL
- `NEXT_PUBLIC_SUPABASE_ANON_KEY` — Supabase anon key

## API Routes

**Video processing:**
`/api/transcript` | `/api/video-info` | `/api/generate-topics` | `/api/generate-summary` | `/api/quick-preview` | `/api/top-quotes`

**AI & chat:**
`/api/chat` | `/api/suggested-questions`

**User data & auth:**
`/api/check-limit` | `/api/check-video-cache` | `/api/video-analysis` | `/api/update-video-analysis` | `/api/save-analysis` | `/api/toggle-favorite` | `/api/link-video` | `/api/notes` | `/api/notes/all` | `/api/csrf-token`

## Supabase Tables

| Table | Key Columns |
|-------|-------------|
| `video_analyses` | `id`, `youtube_id`, `user_id`, `title`, `transcript`, `topics`, `summary` |
| `user_favorites` | `user_id`, `video_analysis_id` |
| `rate_limit_logs` | `identifier`, `action`, `timestamp` |
| `notes` | `id`, `user_id`, `video_id`, `source`, `text`, `metadata` |

## Deployment

Deployed on Vercel with Next.js 15 and Turbopack.

## Session Log

### 2025-12-27
- Initial roadmap sections added
