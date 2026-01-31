Cascading = falling in layers

CSS applies styles in layers of priority. When multiple rules target the same element, the browser doesn’t panic — it cascades through rules and picks the winner using a fixed system.

Correct Priority Order (Top → Bottom)

🥇 !important — Highest
This beats everything, even inline styles.

Example:
p {
  color: blue !important;
}

# <p style="color: red;">Hello</p>

Result: Blue wins.

🥈 Inline CSS
Styles inside the tag itself:
<p style="color: red;">Hello</p>
This beats internal and external CSS.


🥉 Internal CSS
Inside <style> in the HTML file.

4️⃣ External CSS
From .css files.
