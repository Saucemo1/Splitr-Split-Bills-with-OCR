# Splitr Support

Welcome to the Splitr support page.

## FAQ

**What is Splitr?**  
Splitr is a simple tool that helps you scan receipts with OCR and split bills with friends.

**How do I use it?**  
1. Open the app.  
2. Use the camera to scan your receipt.  
3. Review the scanned items.  
4. Split costs among participants.

**Troubleshooting**  
- If OCR has trouble reading your receipt, try better lighting and a flat surface.  
- Make sure you are on the latest version of iOS.  
- If the app crashes, restart and try again.

**Privacy**  
Splitr does not store or share your receipts. Images are only used for OCR processing.

## Contact Us
If you need more help, please email us at:  
📧 mustafasami90@icloud.com

<form id="support">
  <input type="email" name="email" placeholder="Your email" required>
  <input type="text" name="subject" placeholder="Subject" required>
  <textarea name="message" placeholder="Message" required></textarea>
  <button>Send</button>
  <p id="msg" aria-live="polite"></p>
</form>
<script>
document.getElementById('support').addEventListener('submit', async (e) => {
  e.preventDefault();
  const msg = document.getElementById('msg');
  msg.textContent = 'Sending...';
  const body = Object.fromEntries(new FormData(e.target).entries());
  try {
    const r = await fetch('https://YOURDOMAIN.vercel.app/api/contact', {
      method: 'POST', headers: {'Content-Type':'application/json'},
      body: JSON.stringify(body)
    });
    msg.textContent = r.ok ? 'Sent! We’ll reply shortly.' : 'Could not send. Email support@splitrapp.com.';
  } catch {
    msg.textContent = 'Network error. Email support@splitrapp.com.';
  }
});
</script>

