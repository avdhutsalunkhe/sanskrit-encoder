# 🔮 Sanskrit Encoder

[![npm version](https://badge.fury.io/js/%40avdhutsalunkhe%2Fsanskrit-encoder.svg)](https://badge.fury.io/js/%40avdhutsalunkhe%2Fsanskrit-encoder)
[![Downloads](https://img.shields.io/npm/dt/@avdhutsalunkhe/sanskrit-encoder.svg)](https://www.npmjs.com/package/@avdhutsalunkhe/sanskrit-encoder)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Bundle Size](https://img.shields.io/bundlephobia/minzip/@avdhutsalunkhe/sanskrit-encoder)](https://bundlephobia.com/package/@avdhutsalunkhe/sanskrit-encoder)
[![Node Version](https://img.shields.io/node/v/@avdhutsalunkhe/sanskrit-encoder.svg)](https://nodejs.org/)

> The world's first production-ready JavaScript package that transforms English text through ancient Sanskrit wisdom into binary encoding. Bridge 5000-year-old linguistic tradition with modern web technology.


## 📂 Project Documentation Suite

A complete set of professional documentation has been prepared:

- **Implementation Guide (DOCX)** – Full setup, client/server implementation, pipeline explanation, and examples.
- **API Reference (Markdown)** – Detailed function/class reference.
- **Developer Guide (Markdown)** – Contribution, development, and architecture notes.
- **Research Paper (LaTeX)** – Academic foundation and technical depth.

**Project Structure**
sanskrit-encoder/
├── docs/
│ ├── Implementation_Guide.docx
│ ├── API_Reference.md
│ ├── Developer_Guide.md
│ └── Research_Paper.tex
├── src/
│ ├── client/
│ ├── server/
│ ├── core/
│ └── utils/
├── examples/
│ ├── basic-usage.js
│ ├── express-server.js
│ └── secure-implementation.js
├── tests/
├── README.md
└── package.json

## 🚀 Getting Started

### 1. Installation
npm install @avdhutsalunkhe/sanskrit-encoder
2. Client-Side Usage
javascript
Copy code
import { SanskritEncoderClient } from '@avdhutsalunkhe/sanskrit-encoder/client';

const encoder = new SanskritEncoderClient();

(async () => {
  const result = await encoder.encode("Hello World", {
    addChecksum: true,
    includeMetadata: true
  });

  console.log(result.sanskrit);  // → "हेल्लो वर्ल्ड"
})();
3. Server-Side Usage
javascript
Copy code
const { SanskritEncoderServer } = require('@avdhutsalunkhe/sanskrit-encoder/server');
const server = new SanskritEncoderServer();

(async () => {
  const decoded = await server.decode(encodedData, { verifyChecksum: true });
  console.log(decoded.decoded);
})();
4. Express.js API Example
javascript
Copy code
const express = require('express');
const { SanskritEncoderServer } = require('@avdhutsalunkhe/sanskrit-encoder/server');

const app = express();
const encoder = new SanskritEncoderServer();
app.use(express.json());

app.post('/api/decode', async (req, res) => {
  try {
    const result = await encoder.decode(req.body);
    res.json({ success: true, decoded: result.decoded });
  } catch (err) {
    res.status(400).json({ success: false, error: err.message });
  }
});

app.listen(3000, () => console.log("API running on port 3000"));
🔄 Processing Pipeline
English → Sanskrit
"H" → "ह", "e" → "े", "l" → "ल", "o" → "ो"

Sanskrit → Custom Code
"ह" → "1x3", "े" → "0y2"

Code → Binary
"1x30y2..." → "0011000101111000..."

Binary → Transmission
Ready for secure storage or network transfer.

🔐 Security Features
Session-based secure encoding

AES encryption support

Integrity checks with checksum

Batch encoding & caching for performance

🌍 Real-World Applications
📖 Education – Sanskrit learning apps with live character mapping.

💬 Secure Messaging – Encrypted chat with binary transmission.

📂 Data Archival – Cultural manuscript preservation in binary + Sanskrit.

🧪 Testing
Unit tests ensure encoding/decoding integrity:

javascript
Copy code
describe('Sanskrit Encoder', () => {
  it('should encode and decode correctly', async () => {
    const original = "Test message";
    const encoded = await encoder.encode(original);
    const decoded = await server.decode(encoded);
    expect(decoded.decoded).toBe(original);
  });
});

🤝 Contributing
Pull requests are welcome!
For major changes, please open an issue first to discuss the proposal.

📜 License
MIT License © 2025 Avdhut Salunkhe
