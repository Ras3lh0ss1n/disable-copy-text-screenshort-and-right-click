# disable-copy-text-screenshort-and-right-click
How to Use: - Go to your Blogger dashboard. - Navigate to Theme > Customize > Edit HTML. - Paste this code inside the &lt;head> or &lt;body> section. This script prevents users from copying text, taking screenshots, and using right-click functionality.

<style>
/* Disable text selection */
body {
    -webkit-user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
    user-select: none;
}
</style>

<script>
// Disable right-click
document.addEventListener("contextmenu", function(event) {
    event.preventDefault();
});

// Disable key combinations for copying and screenshots
document.addEventListener("keydown", function(event) {
    if (event.ctrlKey && (event.key === 'c' || event.key === 'u')) {
        event.preventDefault();
    }
    if (event.key === 'PrintScreen') {
        event.preventDefault();
        alert("Screenshots are disabled!");
    }
});

// Blank out clipboard to prevent copying
document.addEventListener("copy", function(event) {
    event.clipboardData.setData("text/plain", "Copying is disabled on this site.");
    event.preventDefault();
});
</script>
