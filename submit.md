---  
layout: page  
title: Submit  
permalink: /submit/  
---  
<div class="about-container">
    <div class="sparkles sparkle1"></div>
    <div class="sparkles sparkle2"></div>
    <div class="sparkles sparkle3"></div>

    <script type="text/javascript">
        var submitted = false;
    </script>

    <!-- Hidden iframe to handle form submission -->
    <iframe name="hidden_iframe" id="hidden_iframe" style="display:none;" 
            onload="if(submitted) { window.location='/thanks/'; }">
    </iframe>

    <!-- Styled form with input fields -->
    <form action="https://docs.google.com/forms/d/e/1FAIpQLScczjeCsdTlcDfravUGfl5LOpExWUJW4-4jkE-dto0mOjsPbQ/formResponse" 
          method="post" target="hidden_iframe"
          onsubmit="submitted=true;" class="styled-form">

        <label for="entry.178092692">SPILL YOUR THOUGHTS</label>
        <input type="text" name="entry.178092692" id="entry.178092692" required placeholder="Type here...">

        <input type="submit" value="SEND">
    </form>
</div>