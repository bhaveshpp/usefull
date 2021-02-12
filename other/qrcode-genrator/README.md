## QR Code Generator

```

<textarea class="form-control" id="url" placeholder="Past Code" style="height: 85px;"></textarea>

<div class="img-thumbnail">
  <a href="https://chart.googleapis.com/chart?chs=300x300&cht=qr&chl=&choe=UTF-8" id="link">
    <img id="img" src="https://chart.googleapis.com/chart?chs=300x300&cht=qr&chl=&choe=UTF-8">
  </a>
</div>
      
$(document).ready(function(){
	$("#url").on("change keyup paste", function() {
        var url = $('#url').val();
        var lbl_url = "https://chart.googleapis.com/chart?chs=300x300&cht=qr&chl="+url+"&choe=UTF-8"
     	$('#img').attr('src', lbl_url);
     	$('#link').attr('href', lbl_url);
	});
});

```
