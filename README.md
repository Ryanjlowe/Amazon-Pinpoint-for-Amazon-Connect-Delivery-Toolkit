# Amazon Pinpoint for Amazon Connect Delivery Toolkit

This repository serves as a guide for system integrators who have experience working with Amazon Connect and are looking for ways to expand their set of opportunities by introducing Amazon Pinpoint to the Amazon Connect environment.  Below are a set of use-cases that showcase different integration points between Amazon Connect and Amazon Pinpoint and the value that Amazon Pinpoint brings.

## Table of Contents

* [What is Amazon Pinpoint](#What-is-Amazon-Pinpoint)
* [Use-Case: Call Deflection](#Use-Case-Call-Deflection)
* [Use-Case: Send Campaign Notifications](#Use-Case-Send-Campaign-Notifications)
* [Use-Case: Transactional Outbound Communications - Email, SMS, etc](#Use-Case-Transactional-Outbound-Communications---Email-SMS-etc)
* [Use-Case: Omni-Channel Customer Segmentation / Insights](#Use-Case-Omni-Channel-Customer-Segmentation--Insights)
* [Use-Case: Augment Customer Profiles with Marketing Data](#Use-Case-Augment-Customer-Profiles-with-Marketing-Data)
* [Use-Case: Agent Chat over SMS](#Use-Case-Agent-Chat-over-SMS)
* [Use-Case: Assign Agent Tasks using Amazon Pinpoint Journeys](#Use-Case-Assign-Agent-Tasks-using-Amazon-Pinpoint-Journeys)
* [Other Amazon Pinpoint Resources](#Other-Amazon-Pinpoint-Resources])

## What is Amazon Pinpoint
Amazon Pinpoint is a multi-channel digital engagement service. It is a part of the Customer Engagement suite of services, enabling customers to send both promotional and transactional messages across email, SMS, push notification, voice, and custom channels.  For more details, and a quick guide to Pinpoint terms, see [Amazon Pinpoint Key Concepts](pinpoint_detail/README.md).

See the [Other Amazon Pinpoint Resources](#Other-Amazon-Pinpoint-Resources]) below for official documentation, reference architectures with full CloudFormation source code, fully-vetted AWS Solutions, and recorded webinars and other videos.

## Use-Case: Call Deflection

Call deflection can be an extremely valuable tool for AWS customers to reduce their overall call center costs.  With call deflection, we look to resolve end-customer requests via a different channel.  Amazon Connect introduced chat as a mode for end-customers to get assistance from a live agent without needing to call into the call center.  

Using Amazon Pinpoint for SMS introduces a few different ways that we can offer more call deflection options.  Amazon Pinpoint has [two-way SMS functionality](https://docs.aws.amazon.com/pinpoint/latest/userguide/channels-sms-two-way.html) that can be enabled so that Amazon Pinpoint can be used to send outgoing SMS text messages and process incoming SMS responses from end-customers.  In this way, customers can build synchronous or asynchronous conversational mechanisms on-top of Amazon Pinpoint's two-way SMS.


### Solution: [Amazon Pinpoint SMS Chat Bot](https://aws.amazon.com/blogs/messaging-and-targeting/create-an-sms-chatbox-with-amazon-pinpoint-and-lex/)

[Amazon Lex](https://aws.amazon.com/lex/) is an AI service for building conversation interfaces into any application using voice or text. Amazon Lex has already demonstrated its ability to perform standard tasks like Appointment reminders, confirmations, and automatic rescheduling.

[Amazon Lex can be integrated into Amazon Pinpoint to create a two-way SMS chat bot](https://aws.amazon.com/blogs/messaging-and-targeting/create-an-sms-chatbox-with-amazon-pinpoint-and-lex/) that can be used to deliver Amazon Lex's capabilities over the SMS channel.

<img src="images/lexpinpoint.png" height="300" />

This solution can be extended to include a [seamless handoff to Amazon Connect](https://aws.amazon.com/blogs/messaging-and-targeting/creating-a-seamless-handoff-between-amazon-pinpoint-and-amazon-connect/) to allow for scenarios that Amazon Lex cannot be coded to handle.

<img src="images/PinpointConnectSolution.png" height="400" />


### Solution: [Amazon Pinpoint SMS Connect Chat Connector](https://github.com/Ryanjlowe/amazon-pinpoint-sms-connect-chat)

Amazon Connect's chat experience can be extended to enable using Amazon Pinpoint's two-way SMS as a delivery mechanism.  In this way, call center agents are able to field questions from the website's chat interface and chat messages sent via SMS.  Further, this mechanism could be deployed initiated directly from an inbound call flow allowing the call to be deflected to an agent that can handle multiple chat sessions simultaneously.

<img src="images/chat_screenshot.png" height="400" />


The [Amazon Pinpoint SMS Connect Chat Connector](https://github.com/Ryanjlowe/amazon-pinpoint-sms-connect-chat) is a POC showcasing these capabilities.  Customers can follow the pattern and implement their own SMS to chat flows very quickly.

<img src="images/chat_arch.png" height="400" />


## Use-Case: Send Campaign Notifications

Amazon Pinpoint has three channels available natively out of the box that work with campaigns and journeys: Email, SMS, and Push for Mobile Devices.  Additionally, customers can create their own [custom channels](https://docs.aws.amazon.com/pinpoint/latest/developerguide/channels-custom.html) allowing marketers to send messages across any "channel" using any service that can be reached by an AWS Lambda function.  

The Amazon Pinpoint team has [created and open-sourced an Amazon Connect custom channel](https://github.com/aws-samples/amazon-pinpoint-connect-channel).  This channel can be dropped into a campaign or journey to trigger and outbound call via Amazon Connect. As this [blog points out, this can be used to send voice appointment reminders](#https://aws.amazon.com/blogs/messaging-and-targeting/send-voice-appointment-reminders-using-amazon-pinpoint-custom-channels-and-amazon-connect/) allowing an interactive experience where end-customers could press a button to speak to an agent if needed.  Marketers can use Amazon Pinpoint's segmentation and targeting capabilities to target end-customers to receive an outbound call just like they would for email or SMS as a channel.

<img src="images/Connectoutbound_architecture.png" height="400" />

## Use-Case: Transactional Outbound Communications - Email, SMS, etc

## Use-Case: Omni-Channel Customer Segmentation / Insights

## Use-Case: Augment Customer Profiles with Marketing Data

## Use-Case: Agent Chat over SMS

## Use-Case: Assign Agent Tasks using Amazon Pinpoint Journeys


## Other Amazon Pinpoint Resources
* [Amazon Pinpoint Home](https://aws.amazon.com/pinpoint/)
* [AWS Digital User Engagement Videos and Recorded Webinars](https://awsdue.tv/)
* [Digital User Engagement Reference Architectures](https://github.com/aws-samples/digital-user-engagement-reference-architectures)
* [AWS Solutions](https://aws.amazon.com/solutions/implementations/?solutions-all.sort-by=item.additionalFields.sortDate&solutions-all.sort-order=desc&solutions-all.q=pinpoint&solutions-all.q_operator=AND)
* [Amazon Pinpoint Documentation](https://docs.aws.amazon.com/pinpoint/)
