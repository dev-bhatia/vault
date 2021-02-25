# Embed Youtube Video in Bootstrap Modal

### CSS

Make the video fill up the entire modal.

```css
.yt-video-container {
  position: relative;
  padding-bottom: 56.25%;
  padding-top: 30px;
  height: 0;
  overflow: hidden;
}

.yt-video-container iframe,
.yt-video-container object,
.yt-video-container embed {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}
```

### JS

Stop the video to continue playing once the modal is closed.

```js
$("#Modal-id").on("hidden.bs.modal", function (e) {
  $("#Modal-id iframe").attr("src", $("#Modal-id iframe").attr("src"));
});
```

### Example

This example is using Bootstrap v4.6

```html
<html>
  <head>
    <!-- LINK THE CSS FROM CDN -->
    <link
      rel="stylesheet"
      href="https://cdn.jsdelivr.net/gh/dev-bhatia/vault@main/web/bootstrap-yt-modal.css"
    />
  </head>

  <body>
    <!-- UCSD Webinar Video MODAL -->
    <div class="modal fade" id="UCSDWebinarModal" role="dialog">
      <div class="modal-dialog modal-lg modal-fullscreen modal-dialog-centered">
        <div class="modal-content">
          <div class="modal-header">
            <h5 class="modal-title">UCSD Webinar</h5>
            <button
              type="button"
              class="btn btn-danger btn-sm"
              data-dismiss="modal"
            >
              <i class="fas fa-times"></i>&nbsp;Close
            </button>
          </div>
          <div class=" modal-body yt-video-container">
            <center>
              <iframe
                id="ytplayer"
                type="text/html"
                width="720"
                height="405"
                src="https://www.youtube.com/embed/5sZXZ7gAxU8"
                frameborder="0"
                allowfullscreen
              ></iframe>
            </center>
          </div>
        </div>
      </div>
    </div>
    <!-- STOP Video Playback in Modal for UCSDWebinarModal -->
    <script>
      $("#UCSDWebinarModal").on("hidden.bs.modal", function (e) {
        $("#UCSDWebinarModal iframe").attr(
          "src",
          $("#UCSDWebinarModal iframe").attr("src")
        );
      });
    </script>
  </body>
</html>
```
