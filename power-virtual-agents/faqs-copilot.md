---
title: FAQ for Copilot
description: This FAQ provides information about the AI technology used for the Copilot capability in Microsoft Copilot Studio, along with key considerations and details about how the AI is used, how it was tested and evaluated, and any specific limitations.
ms.date: 7/30/2023
ms.custom: 
  - responsible-ai-faqs
ms.topic: article
author: iaanw
ms.author: iawilt
ms.reviewer: iawilt
---

# FAQ for Copilot

[!INCLUDE[pva-rebrand](includes/pva-rebrand.md)]

These frequently asked questions (FAQ) describe the AI impact of the Copilot feature in Microsoft Copilot Studio.

## What is Copilot?
The system is designed to generate a single bot topic from a human-written description.

## What are Copilot's capabilities?

 It combines the natural language understanding models already in Microsoft Copilot Studio with Azure OpenAI to:

- Understand what the bot maker wants to achieve by parsing their request
- Apply knowledge of how nodes within a topic work together, and how a topic should be constructed for the best effect
- Generate a series of connected nodes that together form a full topic
- Use plain language in any node that contains user-facing text that corresponds with the bot maker's request

## What is Copilot's intended use?
The **Create with Copilot** option in the Microsoft Copilot Studio canvas lets bot makers simply describe what they want to achieve, and then produces a topic path that achieves that goal.

## How was Copilot evaluated? What metrics are used to measure performance?

The capability was evaluated on a collection of manually curated prompt-and-topic datasets, covering common, edge-case, and offensive content, as well as synthetic generation.

During evaluation, topics generated from the capability were manually reviewed and scored for relevance to the input prompt, usefulness, and offensiveness. 

## What are the limitations of Copilot? How can users minimize the impact of limitations when using Copilot?

The system only supports English. Inaccurate responses may be returned when users converse with the system in languages other than English.

- Your bot must be created in the US region. Other regions, and languages other than English, aren't currently supported.

- This capability may be subject to usage limits or capacity throttling.
 
- Topics generated by the capability are not always perfect, and may not accurately reflect the logic you wanted to implement. 

  - We have implemented mitigations to filter out irrelevant and offensive language from appearing in the configured topic, and the system is designed not to respond when offensive language is detected. 

  - We also monitor output and the feedback that bot users provide to continually improve our content filters. These filters and mitigations are not foolproof.

  > [!NOTE]
  > You should always test and review your bots before publishing them.

## What operational factors and settings allow for effective and responsible use of Copilot?
To get the most out of Copilot, include granular instructions in your description and limit the scope of the description to a single topic. If the generated topic is not what you had in mind or if you�d like to further workshop it, you can modify the topic, also using natural language. 

We also recommend you carefully review generated topics for accuracy, either in the authoring canvas or code editor. 

Feedback you provide on your satisfaction with generated topics will be used to improve system quality. You can provide feedback by selecting thumbs up or thumbs down icon for responses generated through Copilot. You can also include more feedback in free text.


## See also

- [Create (and edit) with Copilot](nlu-authoring.md)
