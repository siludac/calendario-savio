const search = document.getElementById("search");
const results = document.getElementById("results");

search.addEventListener("input", () => {
  const q = search.value.toLowerCase();
  results.innerHTML = "";

  const filtered = data.filter(item =>
    item.cap.includes(q) ||
    item.comune.toLowerCase().includes(q)
  );

  filtered.forEach(item => {
    const div = document.createElement("div");
    div.className = "result";
    div.innerHTML = `
      <strong>${item.cap} - ${item.comune} (${item.provincia})</strong><br>
      Giorni: ${item.giorni.join(", ")}
    `;
    results.appendChild(div);
  });
});
