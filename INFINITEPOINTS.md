### Infinite Points - CMU
*Found by TheXbots, Transcribed (and previously discovered) by Yarnlet*<br>
Summary: A vulnerability allowing for infinite points on CMU CS Academy.<br>

### Issue
When submitting an exercise using the "check" button, a POST request is sent to CMU's backend API, which validates project completion. This request is not encrypted or validated, meaning that by sending a valid POST requests (with authentication) to this endpoint will automatically be accepted.<br>
<br>
![image](https://github.com/splitparty/academy.cs.cmu.edu/assets/135715609/7b9c46d9-d2b7-4b4e-a80a-513078ac1d22)<br>
*Figure 1 : This was done by sending a POST request with a points value of 3*<br>

### Replication
Open DevTools on your browser, go to the "Network" tab, and navigate to any CMU exercise and click the blue "check" button.<br>
![image](https://github.com/splitparty/academy.cs.cmu.edu/assets/135715609/5cf644a4-0fa7-4ebf-96aa-eb640ebd4878)<br>
*Figure 2 : 1.1.3 Smiley face*<br>
<br>
Find the request called "/points" and click on it.<br>
![image](https://github.com/splitparty/academy.cs.cmu.edu/assets/135715609/eb7a7ccb-956f-4d2b-9c2c-ac93c914d5c2)<br>
*Figure 3 : DevTools Network Tab*<br>
<br>
Navigate to the "headers" section and copy the value of the "Authorization" header.<br>
![image](https://github.com/splitparty/academy.cs.cmu.edu/assets/135715609/186eac47-deb8-4d10-9deb-cd09bf79a473)<br>
*Figure 4 : The Token Header*<br>
<br>
Navigate to the "payload" section and copy the json.<br>
![image](https://github.com/splitparty/academy.cs.cmu.edu/assets/135715609/ad9e287b-6af5-44fa-922c-e3eae011cc21)<br>
*Figure 5 : Request Payload*<br>
<br>
Edit the body of the request.<br>
*for example:*<br>
```
{
  "submission_id":21*********,
  "points":1,
  "score":"FAIL",
  "file_version":[76081789,3]
}
```
can be changed to: <br>
```
{
  "submission_id":21*********,
  "points":9999,
  "score":"PASS",
  "file_version":[76081789,3]
}
```
<br>
Finally, perform the request on any API-testing site. If the code returned is 200, the request was successful.<br>
A valid request would look something like this; tested on reqbin.com<br>
![image](https://github.com/splitparty/academy.cs.cmu.edu/assets/135715609/5b279beb-7547-4549-83c1-19b9ac3e7e10)<br>
![image](https://github.com/splitparty/academy.cs.cmu.edu/assets/135715609/08074dcc-7744-44a7-85d4-14071bd8b0c1)<br>
And it should return:<br>
![image](https://github.com/splitparty/academy.cs.cmu.edu/assets/135715609/93fd4daf-83b4-4a45-80a2-facc5b991d71)<br>
The end result:<br>
![image](https://github.com/splitparty/academy.cs.cmu.edu/assets/135715609/c2b14ea7-3dce-408f-af26-ee1eb5a4723a)














