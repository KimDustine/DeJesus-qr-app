<template>
  <div>
    <div id="reader" style="width: 300px;"></div>
    <p v-if="scannedCode">Scanned Code: {{ scannedCode }}</p>
  </div>
</template>

<script>
import { Html5Qrcode } from 'html5-qrcode'

export default {
  data() {
    return {
      scannedCode: null,
      qrScanner: null,
    }
  },
  mounted() {
    this.startScanner()
  },
  beforeDestroy() {
    if (this.qrScanner) {
      this.qrScanner.stop().then(() => {
        this.qrScanner.clear()
      }).catch(console.error)
    }
  },
  methods: {
    startScanner() {
      const config = {
        fps: 10,
        qrbox: 250
      }

      this.qrScanner = new Html5Qrcode("reader")

      this.qrScanner.start(
        { facingMode: "environment" },
        config,
        (decodedText) => {
          this.scannedCode = decodedText
          this.qrScanner.stop()
        },
        (errorMessage) => {
          // ignore scan errors
        }
      ).catch(err => {
        console.error("Camera start error:", err)
      })
    }
  }
}
</script>
