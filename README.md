# Motion Provider 
<!-- markdownlint-disable first-line-h1 -->
<!-- markdownlint-disable html -->
<!-- markdownlint-disable no-duplicate-header -->

<div align="center">
  <img src="https://raw.githubusercontent.com/yourusername/motion-provider/main/logo.svg" width="40%" alt="Motion Provider" />
</div>
<hr>
<div align="center" style="line-height: 1;">
  <a href="https://motion-provider.dev" target="_blank" style="margin: 2px;">
    <img alt="Documentation" src="https://img.shields.io/badge/Docs-Motion%20Provider-536af5?color=536af5&logoColor=white" style="display: inline-block; vertical-align: middle;"/>
  </a>
  <a href="https://npmjs.com/package/motion-provider" target="_blank" style="margin: 2px;">
    <img alt="NPM" src="https://img.shields.io/badge/npm-motion--provider-cb3837?logo=npm" style="display: inline-block; vertical-align: middle;"/>
  </a>
  <a href="https://github.com/yourusername/motion-provider" target="_blank" style="margin: 2px;">
    <img alt="GitHub stars" src="https://img.shields.io/github/stars/yourusername/motion-provider?style=social"/>
  </a>
</div>

<div align="center" style="line-height: 1;">
  <a href="https://discord.gg/your-invite" target="_blank" style="margin: 2px;">
    <img alt="Discord" src="https://img.shields.io/badge/Discord-Community-7289da?logo=discord" style="display: inline-block; vertical-align: middle;"/>
  </a>
  <a href="https://twitter.com/yourhandle" target="_blank" style="margin: 2px;">
    <img alt="Twitter Follow" src="https://img.shields.io/badge/Twitter-@yourhandle-1DA1F2?logo=twitter" style="display: inline-block; vertical-align: middle;"/>
  </a>
</div>

<div align="center" style="line-height: 1;">
  <a href="https://github.com/yourusername/motion-provider/blob/main/LICENSE" style="margin: 2px;">
    <img alt="License" src="https://img.shields.io/badge/License-MIT-brightgreen"/>
  </a>
</div>

<p align="center">
  <a href="https://motion-provider.dev/docs"><b>Documentation</b>📚</a>
</p>

## 1. Introduction

Motion Provider is a React animation library that simplifies complex motion design through a centralized animation system (CAS). It provides:

- **Atomic Animation Components**: Pre-built motion primitives (`MotionContainer`, `MotionQueue`, `MotionText`)
- **Synchronized Animations**: Coordinate animations across multiple components
- **Dynamic Control**: Real-time animation control with hooks (`useAnimation`)
- **Cross-Platform**: Works with Next.js, React Native, and WebGL

Key differentiators:
- 🌀 Built-in animation queue system
- 🎮 Imperative animation control
- 🌓 Automatic dark mode support
- 📱 Mobile-first responsive animations

<p align="center">
  <img width="80%" src="https://raw.githubusercontent.com/yourusername/motion-provider/main/demo.gif">
</p>

## 2. Features

<div align="center">

| Feature                      | Description                                                                 |
|------------------------------|-----------------------------------------------------------------------------|
| Motion Queue System          | Sequential/parallel animations with linear/exponential delay logic          |
| CAS (Central Animation System) | Centralized control for application-wide animation states                   |
| Animation Presets            | 40+ pre-built animations (fadeIn, rotateClockwise, filterBlurIn, etc.)      |
| Responsive Hooks             | useAnimation, useMotionState, useBreakpoint for dynamic control             |
| TypeSafe API                 | Full TypeScript support with strict animation type checking                 |
| Performance Optimized        | WebGL fallbacks and requestAnimationFrame integration                       |

</div>

## 3. Installation

```bash
npx install motion-provider @motion-provider/core
```

### 4. Getting Started

Below is a basic example demonstrating how to integrate Motion Provider into your React application:

```tsx
import React, { useState } from 'react';
import { MotionContainer, MotionQueue, useAnimation } from 'motion-provider';
import { Button } from '@/components/ui/button';

export default function App() {
  const [reverseAnimation, setReverseAnimation] = useState(false);
  const [stopAnimation, setStopAnimation] = useState(false);
  const animationConfig = useAnimation({
    stopAnimation,
    reverseAnimation,
    recallDuration: 1,
  });

  return (
    <MotionContainer
      elementType="div"
      mode={['fadeIn', 'filterBlurIn']}
      duration={0.5}
      className="app-container"
    >
      <h1>Welcome to Motion Provider</h1>
      <MotionQueue
        elementType="div"
        duration={1}
        delayLogic="linear"
        isDynamicallyQueued
        animations={[
          {
            mode: reverseAnimation
              ? ['rotateRoll', 'fadeOut']
              : ['rotateClockwise', 'fadeIn'],
            duration: 0.5,
          },
          {
            mode: reverseAnimation
              ? ['rotateRoll', 'fadeOut']
              : ['rotateClockwise', 'fadeIn'],
            duration: 0.5,
          },
        ]}
      >
        <Button onClick={() => setReverseAnimation(prev => !prev)}>
          {reverseAnimation ? 'Start Animations' : 'Reverse Animations'}
        </Button>
        <Button onClick={() => setStopAnimation(prev => !prev)}>
          {stopAnimation ? 'Resume Animations' : 'Stop Animations'}
        </Button>
      </MotionQueue>
    </MotionContainer>
  );
}
```
### 5. Documentation & Examples

Motion Provider comes with comprehensive documentation to help you get the most out of its features. Explore the following resources:

- **Component API Reference**  
  Detailed information about each component and hook.

- **Tutorials & Guides**  
  Step-by-step guides for implementing complex animations.

- **Examples**  
  Check out real-world examples demonstrating various use cases:
  - **SaaS SPA App:** Learn motion state management and advanced image animations.
  - **Crypto Landing App:** Implement coloured and controlled animations.
  - **Agency Landing App:** Master text animations and synchronized effects.
  - **NFT Landing App:** Explore layout animations and dynamic motion queues.

<div align="center">
  <img src="assets/example-saas.gif" width="45%" alt="SaaS SPA App Example" style="margin: 10px;">
  <img src="assets/example-crypto.gif" width="45%" alt="Crypto Landing App Example" style="margin: 10px;">
</div>

## Contact
For support and inquiries:

Email: hello@burakdev.com


<a align="center" target="_blank" src="https://buymeacoffee.com/bilenburakf">
  <img width="80%" src="https://cdn.buymeacoffee.com/buttons/bmc-new-btn-logo.svg">
</a>
