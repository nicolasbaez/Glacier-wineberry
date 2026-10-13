# Glacier-wineberry
The stars remind us that we must return home.

![buh](https://github.com/nicolasbaez/Glacier-wineberry/blob/main/xp084.gif)
```javascript
setup = (_) => createCanvas((w = 500), w, WEBGL);
k = 0;
draw = (_) => {
  t = TAU;
  colorMode(RGB, t);
  clear();
  rotateX(k);
  for (i = 0; i < t; i += noise(i) / 2) {
    for (j = 0; j < PI; j += noise(i, j) / 2) {
      r = noise(i, j, k) * w;
      stroke(i, j, k * t);
      strokeWeight(3);
      point(r * sin(i) * cos(j), r * sin(i) * sin(j), r * cos(i));
    }
  }
  if (k == 0) saveGif("xp084.gif", 1000, { delay: 0, units: "frames" });
  k += r / w / 45;
};
