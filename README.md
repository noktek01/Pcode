<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Reset Password by Nok</title>
  <style>
    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      padding: 0;
      font-family: Arial, sans-serif;
      background-color: #f0f6f8;
      display: flex;
      align-items: center;
      justify-content: center;
      height: 100vh;
    }

    .container {
      background-color: white;
      padding: 1.5rem;
      border-radius: 12px;
      width: 100%;
      max-width: 380px;
      box-shadow: 0 6px 16px rgba(0, 0, 0, 0.1);
    }

    h2 {
      text-align: center;
      margin-bottom: 1.2rem;
      color: #333;
      font-size: 18px;
    }

    label {
      display: block;
      margin-bottom: 0.4rem;
      font-weight: bold;
      color: #444;
      font-size: 13px;
    }

    input[type="password"] {
      width: 100%;
      padding: 8px;
      border: 1px solid #ccc;
      border-radius: 6px;
      margin-bottom: 1rem;
      font-size: 14px;
      transition: border-color 0.3s ease;
    }

    input[type="password"]:focus {
      border-color: #007bff;
      outline: none;
    }

    button {
      width: 100%;
      padding: 10px;
      background-color: #007bff;
      color: white;
      font-size: 14px;
      border: none;
      border-radius: 6px;
      cursor: pointer;
      transition: background-color 0.3s ease;
    }

    button:hover {
      background-color: #0056b3;
    }

    .note {
      margin-top: 0.8rem;
      text-align: center;
      font-size: 13px;
      color: #777;
    }

    @media (max-width: 480px) {
      .container {
        margin: 1rem;
        padding: 1rem;
      }
    }
  </style>
</head>
<body>

  <div class="container">
    <h2>Reset Your Password</h2>
    <form onsubmit="handleReset(event)">
      <label for="new-password">New Password</label>
      <input type="password" id="new-password" required />

      <label for="confirm-password">Confirm Password</label>
      <input type="password" id="confirm-password" required />

      <button type="submit">Reset Password</button>
    </form>
    <div class="note" id="note"></div>
  </div>

  <script>
    function handleReset(event) {
      event.preventDefault();
      const newPass = document.getElementById("new-password").value;
      const confirmPass = document.getElementById("confirm-password").value;
      const note = document.getElementById("note");

      if (newPass === confirmPass) {
        note.style.color = "green";
        note.textContent = " Passwords match. Password reset successful (simulated).";
      } else {
        note.style.color = "red";
        note.textContent = " Passwords do not match. Please try again.";
      }
    }
  </script>

</body>
</html>
