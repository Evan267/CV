<template>
    <div class="contact">
      <h2>Contact</h2>
      <div class="contact__web">
        <ul>
          <li><a href="tel:+33660346613"><i class="fas fa-mobile"></i></a></li>
          <li><a href="https://www.facebook.com/evan.berger.5249"><i class="fab fa-facebook-f"></i></a></li>
          <li><a href="mailto:evan.berger@outlook.com"><i class="fas fa-at"></i></a></li>
        </ul>
      </div>
      <div class="contact__print">
        <ul>
          <li><i class="fas fa-mobile"></i> 06 60 34 66 13</li>
          <li><i class="fas fa-at"></i> evan.berger@outlook.com</li>
          <li>CV web<br>
            <p>https://evan-bergercv.netlify.app/</p>
            <img src="../assets/QRcode.svg" alt="QR code du CV web">
          </li>
        </ul>
      </div>
    </div>
</template>

<script>
export default {
  name: 'Contact'
}
</script>