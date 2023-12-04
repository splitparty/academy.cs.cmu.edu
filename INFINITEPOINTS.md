### Infinite Points - CMU
*Found by TheXbots, Transcribed (and previously discovered) by Yarnlet*

### Issue
When submitting an exercise using the "check" button, a POST request is sent to CMU's backend API, which validates project completion. This request is not encrypted or validated, meaning that by sending a valid POST requests (with authentication) to this endpoint will automatically be accepted.<br>
<br>
![image](https://github.com/splitparty/academy.cs.cmu.edu/assets/135715609/7b9c46d9-d2b7-4b4e-a80a-513078ac1d22)<br>
*Figure 1 : This was done by sending a POST request with a points value of 3*<br>

### Replication

