# Deregistering Task Definitions<a name="deregister-task-definition"></a>

If you decide that you no longer need a task definition in Amazon ECS, you can deregister the task definition so that it no longer displays in your `ListTaskDefinition` API calls or in the console when you want to run a task or update a service\.

When you deregister a task definition, it is immediately marked as `INACTIVE`\. Existing tasks and services that reference an `INACTIVE` task definition continue to run without disruption, and existing services that reference an `INACTIVE` task definition can still scale up or down by modifying the service's desired count\.

You cannot use an `INACTIVE` task definition to run new tasks or create new services, and you cannot update an existing service to reference an `INACTIVE` task definition \(although there may be up to a 10\-minute window following deregistration where these restrictions have not yet taken effect\)\.

**Note**  
At this time, `INACTIVE` task definitions remain discoverable in your account indefinitely; however, this behavior is subject to change in the future, so you should not rely on `INACTIVE` task definitions persisting beyond the lifecycle of any associated tasks and services\.

Use the following procedure to deregister a task definition\.

**To deregister a task definition**

1. Open the Amazon ECS console at [https://console\.aws\.amazon\.com/ecs/](https://console.aws.amazon.com/ecs/)\.

1. From the navigation bar, choose the region that contains your task definition\.

1. In the navigation pane, choose **Task Definitions**\.

1. On the **Task Definitions** page, choose the task definition name that contains one or more revisions that you want to deregister\.

1. On the **Task Definition Name** page, select the box to the left of each task definition revision you want to deregister\.

1. Choose **Actions**, **Deregister**\.

1. Verify the information in the **Deregister Task Definition** window, and choose **Deregister** to finish\.