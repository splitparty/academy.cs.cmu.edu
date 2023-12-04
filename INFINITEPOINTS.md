### Infinite Points - CMU
*Found by TheXbots, Transcribed (and previously discovered) by Yarnlet*

### Issue
When submitting an exercise using the "check" button, a POST request is sent to CMU's backend API, which validates project completion. This request is not encrypted or validated, meaning that by sending a valid POST requests (with authentication) to this endpoint will automatically be accepted.<br>
<br>
![image](https://github.com/splitparty/academy.cs.cmu.edu/assets/135715609/7b9c46d9-d2b7-4b4e-a80a-513078ac1d22)<br>
*Figure 1 : This was done by sending a POST request with a points value of 3*<br>

### Replication
Open DevTools on your browser, go to the "Network" tab, and navigate to any CMU exercise and click the blue "check" button.<br>
![image](https://github.com/splitparty/academy.cs.cmu.edu/assets/135715609/5cf644a4-0fa7-4ebf-96aa-eb640ebd4878)<br>
*Figure 2 : 1.1.3 Smiley face*<br>
Find the request called "/points" and click on it.<br>
![image](https://github.com/splitparty/academy.cs.cmu.edu/assets/135715609/eb7a7ccb-956f-4d2b-9c2c-ac93c914d5c2)<br>
*Figure 3 : DevTools Network Tab*<br>




