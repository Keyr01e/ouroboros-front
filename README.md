# Mancinella Frontend (React + Vite)

Includes:
- WebSocket wrapper (src/ws.js)
- Simple WebRTC signalling helpers for voice chat and screen sharing (src/webrtc.js)
- Basic UI (src/App.jsx)

How to run (locally):
1. Unzip mancinella-frontend.zip and `cd mancinella-frontend`.
2. Install dependencies:
   - Using npm: `npm install`
   - or using pnpm/yarn.
3. Set Vite env var for backend WS if needed:
   - create `.env` with `VITE_WS_URL=ws://localhost:8000/ws`
4. Start dev server:
   - `npm run dev`
5. Open browser at the address printed by Vite (usually http://localhost:5173).

Notes:
- This frontend expects a WebSocket-based signaling server that forwards messages between peers in the same room.
- The code uses a simple JSON protocol (types: join, offer, answer, ice, chat). Adapt to your backend messages if they differ.
- For multi-peer rooms this implements mesh-style connections (each peer connects to each other peer).
- Screen sharing uses `getDisplayMedia` and adds tracks to existing RTCPeerConnections.
