document.addEventListener('DOMContentLoaded', () => {
  // 1. Modo Oscuro / Claro con memoria
  const themeToggle = document.getElementById('themeToggle');
  const themeIcon = document.getElementById('themeIcon');
  const brandLogo = document.getElementById('brandLogo');
  const footerLogo = document.getElementById('footerLogo');

  const applyTheme = (isDark) => {
    document.body.classList.toggle('dark-mode', isDark);
    if (themeIcon) themeIcon.textContent = isDark ? '☀️' : '🌙';
    const logoSrc = isDark ? 'assets/logo-blanco.png' : 'assets/logo-magenta.png';
    if (brandLogo) brandLogo.src = logoSrc;
    if (footerLogo) footerLogo.src = logoSrc;
  };

  const savedTheme = localStorage.getItem('mada-theme');
  if (savedTheme === 'dark') {
    applyTheme(true);
  }

  if (themeToggle) {
    themeToggle.addEventListener('click', () => {
      const isDark = !document.body.classList.contains('dark-mode');
      applyTheme(isDark);
      localStorage.setItem('mada-theme', isDark ? 'dark' : 'light');
    });
  }

  // 2. Menú móvil táctil
  const menuToggle = document.getElementById('menuToggle');
  const navLinks = document.getElementById('navLinks');

  if (menuToggle && navLinks) {
    menuToggle.addEventListener('click', () => {
      const isOpen = navLinks.classList.toggle('open');
      menuToggle.setAttribute('aria-expanded', isOpen);
    });

    navLinks.querySelectorAll('a').forEach(link => {
      link.addEventListener('click', () => {
        navLinks.classList.remove('open');
        menuToggle.setAttribute('aria-expanded', 'false');
      });
    });
  }

  // 3. Filtro de categorías del portafolio
  const filterButtons = document.querySelectorAll('.filter-btn');
  const portfolioItems = document.querySelectorAll('.portfolio-item');

  filterButtons.forEach(btn => {
    btn.addEventListener('click', () => {
      filterButtons.forEach(b => b.classList.remove('active'));
      btn.classList.add('active');

      const category = btn.dataset.filter;

      portfolioItems.forEach(item => {
        if (category === 'todos' || item.dataset.category === category) {
          item.classList.remove('hidden');
        } else {
          item.classList.add('hidden');
        }
      });
    });
  });

  // 4. Año automático en footer
  const yearSpan = document.getElementById('year');
  if (yearSpan) {
    yearSpan.textContent = new Date().getFullYear();
  }
});
