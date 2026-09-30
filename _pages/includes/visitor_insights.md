# 👀 Visitor Insights

<div class="visitor-grid" aria-label="Visitor information">
  <div class="visitor-card">
    <i class="fas fa-chart-line" aria-hidden="true"></i>
    <div>
      <small>Visits on this device</small>
      <strong id="localVisitCount" aria-live="polite">—</strong>
    </div>
  </div>

  <div class="visitor-card">
    <i class="fas fa-globe" aria-hidden="true"></i>
    <div class="visitor-ip-copy">
      <small>Your public IP</small>
      <strong id="visitorIp" aria-live="polite">Hidden</strong>
    </div>
    <button class="visitor-ip-button" id="revealVisitorIp" type="button">Show IP</button>
  </div>
</div>

<p class="visitor-note">The visit count is stored only in this browser. Your public IP is requested from ipify only after you click “Show IP” and is not stored by this site.</p>

<script>
(function () {
  const countElement = document.getElementById('localVisitCount');
  const storageKey = 'ruibin-min-homepage-visits';

  try {
    const previousCount = Number.parseInt(window.localStorage.getItem(storageKey) || '0', 10);
    const currentCount = (Number.isFinite(previousCount) ? previousCount : 0) + 1;
    window.localStorage.setItem(storageKey, String(currentCount));
    countElement.textContent = currentCount.toLocaleString();
  } catch (error) {
    countElement.textContent = 'Unavailable';
  }

  const ipElement = document.getElementById('visitorIp');
  const revealButton = document.getElementById('revealVisitorIp');

  revealButton.addEventListener('click', async function () {
    revealButton.disabled = true;
    revealButton.textContent = 'Loading…';

    try {
      const response = await fetch('https://api64.ipify.org?format=json', { cache: 'no-store' });
      if (!response.ok) throw new Error('IP lookup failed');
      const data = await response.json();
      ipElement.textContent = data.ip || 'Unavailable';
      revealButton.textContent = 'Shown';
    } catch (error) {
      ipElement.textContent = 'Unavailable';
      revealButton.disabled = false;
      revealButton.textContent = 'Try again';
    }
  });
})();
</script>
