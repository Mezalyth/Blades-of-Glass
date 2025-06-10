---
draft: true
tags:
  - dev
  - tartot-app
---
## Overview
A tarot-reading app that's text-based. Clean, minimal, and clear.

## Functions

- Store Tarot data such as number, orientation, meanings/keywords, descriptions
- "Shuffle" the deck before pulling cards
- When pulling cards, no art, just text with metadata
- Can pull 10 singular cards or a Duo and Triple once every 24 hours (free)
- (Premium) will allow users to pull as many cards/spreads as desired with no limits
- After a pull/duo/triple, GPT API will interpret the meaning
  
## Plan

- Build web-app first using light framework capable of the above
- Wrap and deploy to Apple App store
- Gauging success, deploy to Google App store

## Dev Notes
### Framework

**Ionic with React**
- Faster for web dev
- Singular codebase
- HTML + CSS + wrapper
