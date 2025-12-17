 
```html
<!DOCTYPE html>
<html>
<head>
  <title>Grow Pak - GP Coin</title>
  <style>
    body { font-family: Arial; background: #f2f2f2; margin: 0; padding: 0; }
    header { background: #006400; color: white; padding: 20px; text-align: center; }
    section { padding: 20px; }
    .card { background: white; padding: 15px; margin-bottom: 15px; border-radius: 8px; }
    input, button { padding: 10px; margin-top: 5px; width: 100%; }
    .hidden { display: none; }
  </style>
</head>
<body>

<header>
  <h1>Grow Pak</h1>
  <p>Founder & CEO: Mr. Faizi</p>
</header>

<section>
  <div class="card">
    <h2>Our Vision</h2>
    <p>At GP Coin, our mission is to empower individuals through a fair, transparent, and community-driven digital currency...</p>
  </div>

  <div class="card">
    <h2>Register</h2>
if (!name || !email || !pass) {
      document.getElementById("regMsg").innerText = "All fields required!";
      return;
    }

    user = { name, email, pass, balance: 0 };
    localStorage.setItem("gp_user", JSON.stringify(user));
    document.getElementById("regMsg").innerText = "Registered successfully!";
    document.getElementById("miningCard").classList.remove("hidden");
  }

  function mine() {
    let saved = localStorage.getItem("gp_user");
    if (!saved) return;

    let now = Date.now();
    let timeGap = now - lastMine;

    if (timeGap < 12 * 60 * 60 * 1000) {
      document.getElementById("mineMsg").innerText = "Come back after 12 hours.";
      return;
    }

    lastMine = now;
    let reward = 100 + (referrals * 50);
    user.balance += reward;
    localStorage.setItem("gp_user", JSON.stringify(user));
    document.getElementById("balance").innerText = user.balance;
    document.getElementById("mineMsg").innerText = `You earned ${reward} GP!`;
  }

  // Auto-load user
  window.onload = () => {
    let saved = localStorage.getItem("gp_user");
    if (saved) {
      user = JSON.parse(saved);
      document.getElementById("miningCard").classList.remove("hidden");
      document.getElementById("balance").innerText = user.balance;
    }
  }
</script>

</body>
</html
```

---
