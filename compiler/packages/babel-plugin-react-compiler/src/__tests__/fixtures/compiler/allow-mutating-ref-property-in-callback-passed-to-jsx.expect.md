
## Input

```javascript
// @validateRefAccessDuringRender
import { useRef } from "react";

function Component() {
  const ref = useRef(null);

  const onClick = () => {
    if (ref.current !== null) {
      ref.current.value = "";
    }
  };

  return (
    <>
      <input ref={ref} />
      <button onClick={onClick} />
    </>
  );
}

export const FIXTURE_ENTRYPOINT = {
  fn: Component,
  params: [{}],
};

```

## Code

```javascript
import { c as _c } from "react/compiler-runtime"; // @validateRefAccessDuringRender
import { useRef } from "react";

function Component() {
  const $ = _c(8);
  const ref = useRef(null);
  let t0;
  if ($[0] === Symbol.for("react.memo_cache_sentinel")) {
    t0 = () => {
      if (ref.current !== null) {
        ref.current.value = "";
      }
    };
    $[0] = t0;
  } else {
    t0 = $[0];
  }
  const onClick = t0;
  let t1;
  if ($[1] !== onClick) {
    t1 = <button onClick={onClick} />;
    $[1] = onClick;
    $[2] = t1;
  } else {
    t1 = $[2];
  }
  let t2;
  if ($[3] !== ref) {
    t2 = <input ref={ref} />;
    $[3] = ref;
    $[4] = t2;
  } else {
    t2 = $[4];
  }
  let t3;
  if ($[5] !== t2 || $[6] !== t1) {
    t3 = (
      <>
        {t2}
        {t1}
      </>
    );
    $[5] = t2;
    $[6] = t1;
    $[7] = t3;
  } else {
    t3 = $[7];
  }
  return t3;
}

export const FIXTURE_ENTRYPOINT = {
  fn: Component,
  params: [{}],
};

```
      
### Eval output
(kind: ok) <input><button></button>