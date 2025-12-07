---
navigation:
  label: "ตัวอย่างโปรแกรม"
  to: "example"
---

# 📢 ตัวอย่างโปรแกรม

source code ต่อไปนี้ หากเข้าใจก็ถือว่าพร้อมสำหรับการฝึกงานแล้ว

```html
<!DOCTYPE html>
<html>

<body>
    <label>Line:</label>
    <input id="line" type="number" value="30">
    <button onclick="draw()">Draw</button>
    <pre id="out"></pre>
</body>

<script>
    draw()

    function draw() {
        const c = parseInt(document.getElementById("line").value)
        const CHAR = "+"
        let a = -c
        let b = 0
        let out = ""

        while (a <= c) {
            b = Math.round(Math.sqrt(c * c - a * a) - 1)
            out += CHAR.padStart(c - b)
            if (b > 0)
                out += CHAR.padStart(b + b)
            out += "\n"
            a += 2
        }

        document.getElementById("out").textContent = out
    }
</script>

<style>
    body {
        background: #000;
        color: #00ff55;
        font-family: "Courier New", monospace;
        padding: 20px;
    }
</style>

</html>
```
