# Omnipod and Omnipod DASH Pump

## Pair Pod

You'll be pairing a pod every 2 or 3 days (max pod life is 80 hours).

You'll see this screen every time you ask Loop to `Pair New Pod`.

The Omnipod Common pairing protocol is the same for all pods. The difference is that Omnipod requires a RileyLink compatible device and Omnipod DASH does not. There are also slight differences in some of the text and graphics, e.g., Omnipod DASH uses a blue needle cap and Omnipod has a clear needle cap.

Graphic below shows the Pair Pod screen for Omnipod (left) and Omnipod DASH (right).

![pair pod screens for Omnipod and Omnipod DASH](img/loop-3-pair-pod-duo.svg){width="500"}
{align="center"}

!!! abstract ""
    Loop walks you through each step of the filling, pairing, priming, attaching and insertion process.

    It makes sure you are really ready to do the insertion.

    Please watch the video to see the full process before pairing your first pod.


A [video is found here for pairing a DASH pod](https://drive.google.com/file/d/1mN5s8-oorvoa-gbjAaYbnUnl_-vvuhNC/view?usp=sharing). Once the pod starts priming in the video, you may want to skip forward (it takes about a minute to prime).

!!! danger "Keep Gear Close"
    * Make sure phone (and RileyLink if using one) are close to the pod before you tap Pair Pod
        * Do NOT move devices away from the pod until you see the blue check mark and the `Continue` button on the phone screen
        * You can then move away to attach the pod to your body
    * Make sure phone (and RileyLink if using one) are close to the pod before you tap `Insert Cannula`
        * Do NOT move devices away from the pod until you see the blue check mark and the `Continue` button on the phone screen

The Screen that says Setup Complete allows you to change the Scheduled Reminder for this pod if you want a different reminder time (including none) from your usual setting.

* This only changes the reminder for this one pod
* If you want to change all future reminders, tap on Notifications to modify the Reminder Default
* In that same location, you can also change notification for the current pod


## Pod Status

The Pod Status screen is shown in the graphic below. The dashed green outline indicates the `Device` portion that is found only for the Omnipod.  All other features of the screen are common for Omnipod and Omnipod DASH.

![consolidated view of the status and command screen for Omnipod or Omnipod DASH pumps](img/loop-3-omnipod-screen.svg){width="250"}
{align="center"}

### Play Beeps

If you want to make sure Loop can talk to your pod, click on the sound icon (highlighted by the red box) in the graphic above. If the icon is greyed out - that means Loop is having a communication issue reaching your pod. (More on this in the [Alert Screens](#alert-screens) section.)

!!! tip "Other Uses"
    * Find (or startle) your child
    * Find the pod that fell off overnight and is mixed with the laundry

### Pod Expires

* This line provides a count-down until expiration along with a graphical representation of pod life
    * Once you are on the final day, the time remaining until expiration starts to report in Hours and Minutes
    * The solid bar is proportional to pod hours since activation
        * It is blue for the first 48 hours
        * It is orange for the last 24 hours and also appears in the [HUD Pump Status](displays_v3.md#pump-status-icon) icon
        * After expiration, a full-width red bar is shown here and in the HUD Pump Status icon
* Once the pod officially expires, at 72 hours, there is an 8 hour grace period
    * Insulet does not guarantee the pod will keep working that long, but it often does
    * A note will appear on the [Pod Status](#pod-status) screen with count-down text:
        * Change pod now. Insulin delivery will stop in HH hours, MM minutes or when no more insulin remains

### Basal Report

The next row changes the label depending on the situation. In all cases, the current basal rate is reported.

| <div style="width:55px"></div> Label | Description |
|---|---|
|Scheduled Basal|Pod is running the scheduled basal rate|
|Insulin Delivery|Pod is running an automated or manual temporary basal rate|


### Insulin Remaining

Pods start reporting reservoir values when 50 U are left.

| <div style="width:55px"></div> Value | Meaning |
|---|---|
|50+ U|Pod reservoir is greater than 50 U|
|Value U|Pod reservoir is estimated to be at least as great as the indicated value.|
| 0 U|Pod will attempt to deliver up to 4 U after it reports 0 U.<br><br> This is not guaranteed. The pod senses when it is not successful delivering pulses and that can happen before 4 U have been delivered.|


## Activity

### Suspend Delivery

You may want to consider using a [Manual Temp Basal](#manual-temp-basal) of 0 U/hr instead of suspend.

Tapping on `Suspend Delivery` brings up a timed reminder screen. You can choose to be reminded (via a beep on the pod itself) with 4 choices (or you can cancel the request):

* 30 minutes
* 1 hour
* 1 hour 30 minutes
* 2 hours

After you select the reminder time, Loop issues a command to the pod to halt all insulin delivery: basals, temp basals, and boluses in progress. The label on the `Suspend Delivery` row changes to `Suspending` while Loop is communicating with the pump. When the label changes to `Resume Delivery`, all insulin delivery is stopped until the user resumes using the [HUD Status Row](displays_v3.md#hud-status-row) or the [Pod Status](#pod-status) screen.

As long as the spinning icon is spinning, Loop is trying to execute the Suspend or Resume command. If it fails to complete, a modal alert will appear that says "Error Suspending" or "Failed to Resume Insulin Delivery" which you must acknowledge. You must then repeat the command to try again. For Omnipod, make sure your RileyLink device is powered on and close to the phone and pod.

When the phone is in portrait mode, so the HUD is visible:

* The user is alerted that pump is suspended by the HUD [Pump Status Icon](displays_v3.md#pump-status-icon).

![pump status icon when suspended](img/loop-3-pump-alert-suspended.svg){width="150"}
{align="center"}

* The [HUD Status Row](displays_v3.md#hud-status-row) message can be tapped to resume delivery.

![status row message when pump is suspended](img/status-row-pump-suspended.svg){width="300"}
{align="center"}

If you request a manual bolus with Loop while a pod is suspended, Loop will send a notification that Bolus Failed with instructions that Pump is Suspended, Resume Delivery.  In other words, you must resume delivery before you will be allowed to bolus with pods.

At the end of the reminder time, an alert beep is issued by the pod and a modal alert will be provided on the Loop app. You must acknowledge the modal alert on the phone to silence future pod alerts.

!!! danger "Manually Resume Insulin Delivery"
    The halt of all insulin delivery continues until you manually resume. There is no automatic resumption of basal insulin from a suspend command.

    If you select a Manual Temp Basal command of 0 U/hr instead of Suspend:

    * Basal Delivery automatically resumes at the end of the selected duration without need for Loop to command it
    * At the end of the duration, Loop will restore Closed Loop, if you were in closed loop when you issued the Manual Temp Basal command
    * There are no beeps on the pod to remind you to resume insulin delivery

### Manual Temp Basal

Tap on the `Set Temporary Basal Rate` to select a Manual Temp Basal.

This brings up the `Temporary Basal` screen shown on the left of the graphic below. 

* You can select any basal rate from 0 U/hr to your maximum basal rate set in [Delivery Limits](therapy-settings.md#maximum-basal-rate)
* You can choose any duration up to 12 hours in half-hour increments
* Once you select rate and duration and tap `Set Temporary Basal`, Loop goes into Open Loop mode and the pod is commanded to that rate and duration. 

In other words, you can leave your phone behind and the selected basal rate continues for the selected basal duration. There will be no automated adjustments of delivery for the temp basal duration.<br><br>

![screens used to configure, track and cancel manual temp basal rate](img/manual-temp-basal.svg){width="600"}
{align="center"}


Once the manual temp basal command is sent to the pod, Loop updates displays as shown in the graphic above

* [Pod Status](#pod-status) screen:
    * The [Basal Report](#basal-report) updates with the new rate and label indicates `Insulin Delivery`
    * The row label changes to `Cancel Manual Basal` and reports the time remaining until the temp basal expires
* Main screen (refer to red rectangle highlights):
    * The HUD [Loop Status Icon](displays_v3.md#loop-status-icon) changes to an `Open Loop` icon and the HUD [Pump Status Icon](displays_v3.md#pump-status-icon) indicates `Manual Basal`
    * The [Insulin Delivery](displays_v3.md#insulin-delivery-chart) plot indicates the planned duration of the manual temp basal
    * The [Glucose Prediction](displays_v3.md#glucose-chart) updates using that assumed change in insulin delivery

So long as you were in Closed Loop before requesting the Temp Basal, Loop returns to Closed Loop automatically when the duration ends or you cancel the temporary basal.

!!! info "Automatic Resumption of Scheduled Basal"
    The phone does not need to be in contact with the pod for insulin delivery to return to scheduled basal at the end of the selected duration. That duration is commanded along with the temporary rate. Once the pod accepts that command, and you'll get an error message if it does not, the pod will resume scheduled basal rate without further commanding, so long a there is insulin in the reservoir and a pod fault does not occur.

## Configuration

### Notification Settings

Placeholder for the Notification Settings section.

### Confidence Reminders

Placeholder for the Confidence Reminders section.

### Insulin Type

You selected [insulin type](add-pump.md#insulin-type) when connecting to this pump.

Tap on this row if you switch to a different type of insulin.

* The model used by Loop for all the rapid insulin brands are the same, but it's a good idea to record if you change brands - some people notice differences
* If you switch between rapid and ultra-rapid insulin, you need to let Loop know so it will use the appropriate model

## Previous Pod Information

Placeholder for the Previous Pod Information section.

## Alert Screens

There are a number of modal screens to alert you of notifications and problems.

### Notifications

Placeholder for the Notifications section.

### Error Messages

Placeholder for the Error Messages section.