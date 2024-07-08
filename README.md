# jenkins-example1
There are two methods for triggering builds in Jenkins when changes occur in Git repository:

**1. GitHub Webhooks for GITScm Polling** \
        a. GitHub webhooks are a notification system that notifies Jenkins when any change occurs in the repository.\
        b. You configure a webhook URL within your Git repository settings on GitHub. Then, whenever an event is triggered on GitHub (e.g., push, pull request), it sends a notification to the webhook URL, prompting Jenkins to poll the Git repository for changes. 

**To congigure your pipeline**  
      1. Go to Pipeline from the dashboard.\
      2. Select Configuration.\
      3. Go to the Trigger section.\
      4. Check the **GitHub Webhooks for GITScm Polling** option.\
         ![Screenshot (18)](https://github.com/ebrahim0000p0/jenkins-example1/assets/57353913/e0b4f20b-d86e-4706-b0c3-f5cbfe4033c3)

  **To add the webhook URL to your Git repository:**\
    1. Go to your repository settings. \
    2. Navigate to the Webhooks section. \
    3. Enter the payload URL in the appropriate.

  <img width="1110" alt="git2" src="https://github.com/ebrahim0000p0/jenkins-example1/assets/57353913/0b0fc0c9-301d-43bc-b0fd-aa4abe5dca9f">

  **Pros:**\
        1. Faster response: Reacts immediately to events on GitHub. \
        2. Reduced polling: Only polls when notified by GitHub, minimizing unnecessary checks.\
        3. Scalability: Well-suited for heavily updated repositories or projects requiring real-time build triggers.\


  **Cons:**\
      1. Configuration overhead: Requires setting up webhooks within each repository.\
      2. Potential delays: Relies on GitHub's webhook delivery speed, which might introduce slight delays.\

  **Visual Representation**\
  
  ```
  +-------------------+          +-------------------+          +-------------------+
  |       GitHub      | ------> | Webhook Notification | ------> |      Jenkins      |
  +-------------------+          +-------------------+          +-------------------+
                               (triggered by push, pull request, etc.)
  ```

**2. Poll SCM**\
  Jenkins periodically checks the Git repository for changes using a cron-based schedule.\
      **To configure your pipeline:** \
      1. Go to Pipeline from the dashboard. \
      2. Select Configuration. \
      3. Go to the Trigger section. \
      4. Check the **Poll SCM** option \
           ![Screenshot (19)](https://github.com/ebrahim0000p0/jenkins-example1/assets/57353913/1851b81e-a08c-489b-81fb-feb36b9c2d08)

  **Pros**\
      1. Simplicity: No additional setup within GitHub required.\
  
  **Cons:**\
      1. Potential inefficiency: Frequent polling can overload Jenkins .\
      2. Delayed response: Jenkins polls at defined intervals, leading to a potential delay in triggering builds compared to webhooks.\
      
  
  **Visual Representation:**\

```
+-------------------+          +-------------------+
|       Jenkins      |          |      Git SCM      |
+-------------------+          +-------------------+
                  |
                  | (Periodic Polling)
                  v
           (Triggered Build)
```
