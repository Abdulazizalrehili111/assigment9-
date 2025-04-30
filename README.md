í´¹ 4.1 Test the S3 Website
Action:

Open your S3 Static Website URL in a browser.

Check:

Page loads with HTML and logos.

Command:

bash
Copy
Edit
curl -I http://yourname-clarusway-assets.s3-website.eu-north-1.amazonaws.com
Expected:

HTTP/1.1 200 OK

í´¹ 4.2 Test the Application Load Balancer (ALB)
Action:

Open the ALB DNS name in a browser.

Check:

The same page from the EC2 NGINX server loads.

Where to find DNS name:

Go to EC2 â†’ Load Balancers â†’ Copy DNS name of your ALB.

í´¹ 4.3 Verify Round-Robin (Load Distribution)
Action: Run this command:

bash
Copy
Edit
for i in {1..5}; do curl -s http://YOUR_ALB_DNS | grep "hostname"; done
Check:

You should see different outputs (from different EC2 instances).

Tip (optional):

Customize the index.html with:

html
Copy
Edit
<h1>Served by: $(hostname)</h1>
í´¹ 4.4 Test Auto Scaling Replacement
Action:

Stop or terminate one EC2 instance from your ASG.

Check:

Auto Scaling Group launches a new instance automatically within a few minutes.
# assigment9-
