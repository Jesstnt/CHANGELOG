# Lorem Ipsum

## Why do we use it?

It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).

![image](/image/mock.avif)

### Video Demo

Here is a video of what we will be building today.

[![](https://markdown-videos-api.jorgenkh.no/youtube/NaGfTvx__kg)](https://youtu.be/NaGfTvx__kg)



### Where can I get some?

First of all, we need to install the library ****[react-canvas-confetti](https://www.npmjs.com/package/react-canvas-confetti).** This is an example of the realistic confetti effect. They have more examples in their [storybook](https://ulitcos.github.io/react-canvas-confetti/)

```tsx
import { useCallback, useEffect, useRef } from 'react';

import ReactCanvasConfetti from 'react-canvas-confetti';

export default function Confetti() {
  const refAnimationInstance = useRef(null);

  const getInstance = useCallback(instance => {
    refAnimationInstance.current = instance;
  }, []);

  const makeShot = useCallback((particleRatio, opts) => {
    refAnimationInstance.current &&
      refAnimationInstance.current({
        ...opts,
        origin: { y: 0.7 },
        particleCount: Math.floor(200 * particleRatio)
      });
  }, []);

  useEffect(() => fire(), []);

  const fire = useCallback(() => {
    makeShot(0.25, {
      spread: 26,
      startVelocity: 55
    });

    makeShot(0.2, {
      spread: 60
    });

    makeShot(0.35, {
      spread: 100,
      decay: 0.91,
      scalar: 0.8
    });

    makeShot(0.1, {
      spread: 120,
      startVelocity: 25,
      decay: 0.92,
      scalar: 1.2
    });

    makeShot(0.1, {
      spread: 120,
      startVelocity: 45
    });
  }, [makeShot]);

  return (
    <ReactCanvasConfetti
      refConfetti={getInstance}
      style={{
        position: 'fixed',
        pointerEvents: 'none',
        width: '100%',
        height: '100%',
        top: 0,
        left: 0
      }}
    />
  );
}
```

### Use it in a component

The usage of the Confetti component is quite straight forward, just use the confetti component in the codebase 🎉 

```jsx
import { useState } from 'react';
import Confetti from './Confetti';

export default function ConfettiLayout() {
  const [isVisible, setIsVisible] = useState(false);

  return (
    <>
      <button onClick={() => setIsVisible(true)}>Fire</button>
      {isVisible && <Confetti />}
    </>
  );
}
```
