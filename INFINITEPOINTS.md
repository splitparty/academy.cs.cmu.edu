### Infinite Points - CMU
*Found by TheXbots, Transcribed (and previously discovered) by Yarnlet*<br>
Summary: A vulnerability allowing for infinite points on CMU CS Academy.<br>

### Issue
When submitting an exercise using the "check" button, a POST request is sent to CMU's backend API, which validates project completion. This request is not encrypted or validated, meaning that by sending a valid POST requests (with authentication) to this endpoint will automatically be accepted.<br>

# IF YOU ARE FROM CMU AND NEED TO REPLICATE THE EXPLOIT PLEASE CONTACT ME
# sadlittlemarlowe@gmail.com













