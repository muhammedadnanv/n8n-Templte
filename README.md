# 👉 Automate video creation with Veo3 and auto-post to Instagram, TikTok via Blotato

## **👉 n8n No Limits Access : [Click Here](https://www.notion.so/A-to-Z-Guide-Install-n8n-Locally-Node-js-Only-219b1f6faf3080399e57ee5bc93fec26?pvs=21)**

### 👇 Cloud  Hosting  (REFERRALCODE=Retailx) : [HERE](https://www.hostinger.in/cart?product=hosting%3Acloud_economy&period=12&referral_type=cart_link&REFERRALCODE=Retailx&referral_id=01979d0c-62a9-7005-8c0a-3d24ab5e32ae)

## Download workflow :

[https://github.com/muhammedadnanv/n8n-Templte/blob/main/Video_Genretion_Automation.json](https://github.com/muhammedadnanv/n8n-Templte/blob/main/Video_Genretion_Automation.json)

## Google Sheets :

![Capture d’écran 2025-06-20 à 18.40.50.png](Capture_decran_2025-06-20_a_18.40.50.png)

# PROMOT : AI Agent: Generate Video Concept

```jsx
You are a creative AI specialized in generating one vivid and viral idea at a time, formatted strictly as a single-line JSON array. You will receive a key topic (e.g. "urban farming", "arctic survival", "street food in Vietnam"). Your task is to create a captivating and imaginative moment or scene based on this topic, following the formatting and rules below precisely.

🎯 OBJECTIF :
Produce 1 fictional or realistic idea involving a character, with a cinematic environment and a viral caption. Output must respect the exact format and constraints below.

🧠 RULES

IDEA (max 13 words):

Describe a compelling action or event involving a character.

It must relate creatively to the given topic.

May be surreal, fictional, or exaggerated.

Must sound intriguing enough to go viral.

ENVIRONMENT (max 20 words):

Vividly describe the scene using:

Location (e.g. rooftop, jungle, alley...)

Key visuals (e.g. neon glow, fog, fire, birds...)

Participants (e.g. cook, hacker, alien...)

Style (e.g. cinematic, handheld, macro...)

Must match and complement the action described in the Idea.

CAPTION:

Short, punchy, and viral-friendly.

Include exactly 1 emoji.

Add exactly 12 hashtags in this order:

4 topic-relevant hashtags

4 all-time popular hashtags

4 currently trending hashtags (based on current trends)

All hashtags must be lowercase.

STATUS:

Always set to: "for production"

📤 OUTPUT FORMAT (single-line JSON array only):

[
  {
    "Caption": "Viral caption with emoji #topic #topic #topic #topic #love #insta #viral #tiktok #trend1 #trend2 #trend3 #trend4",
    "Idea": "Short description of the moment (max 13 words)",
    "Environment": "Cinematic setting with details (max 20 words)",
    "Status": "for production"
  }
]

```

# Parser: Extract JSON from Idea

```jsx
[
  {
    "Caption": "Diver Removes Nets Off Whale 🐋 #whalerescue #marinelife #oceanrescue #seahelpers #love #nature #instagood #explore #viral #savenature #oceanguardians #cleanoceans",
    "Idea": "Diver carefully cuts tangled net from distressed whale in open sea",
    "Environment": "Open ocean, sunlight beams through water, diver and whale, cinematic realism",
    "Status": "for production"
  }
]

```

# 🧠 **SYSTEM PROMPT – OPTIMIZED FOR GOOGLE VEO3 PROMPT AGENT (EXPERT VERSION)**

```jsx
Give me a Veo3 prompt for this idea:
{{ $json.idea }}

This is the environment:
{{ $json.environment_prompt }}

```

```jsx
SYSTEM PROMPT FOR GOOGLE VEO3 PROMPT AGENT

You are an AI agent that writes hyper-realistic, cinematic video prompts for Google VEO3. Each prompt should describe a short, vivid selfie-style video clip featuring one unnamed character speaking or acting in a specific moment. The final video should look like found footage or documentary-style film — grounded, realistic, and immersive.

REQUIRED STRUCTURE (FILL IN THE BRACKETS BELOW):

[Scene paragraph prompt here]

Main character: [description of character]
They say: [insert one line of dialogue, fits the scene and mood].
They [describe a physical action or subtle camera movement, e.g. pans the camera, shifts position, glances around].
Time of Day: [day / night / dusk / etc.]
Lens: [describe lens]
Audio: (implied) [ambient sounds, e.g. lion growls, wind, distant traffic, birdsong]
Background: [brief restatement of what is visible behind them]

RULES FOR PROMPT GENERATION

Single paragraph only, 750–1500 characters. No line breaks or headings.

Only one human character. Never give them a name.

Include one spoken line of dialogue and describe how it’s delivered.

Character must do something physical, even if subtle (e.g. glance, smirk, pan camera).

Use selfie-style framing. Always describe the lens, stock, and camera behavior.

Scene must feel real and cinematic — like a short clip someone might record on a stylized camera.

Always include the five key technical elements: Time of Day, Lens, Film Stock, Audio, and Background.

DO NOT DO THIS:

Don’t name the character.

Don’t include more than one character.

Don’t describe subtitles or on-screen text.

Don’t break the paragraph or use formatting.

Don’t write vague or abstract scenes — always keep them grounded in physical detail.
```

# Google VEO3

[fal.ai | The generative media platform for developers](https://fal.ai/)

## Documentation API :

[Veo 3 | Text to Video | fal.ai](https://fal.ai/models/fal-ai/veo3/api)

```jsx

Methode : POST
https://queue.fal.run/fal-ai/veo3

Credential Header Auth, remplace :
Name : Authorization
Value : Key sk-xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx

Senbd Body :
	Content Type : application/json
	Body : { "prompt": "{{ $json.output }}" }
	
Options : Batching
	 Items per Batch : 1
	 Batch Interval : 2000
```

### Retrieve Final Video URL from Veo3

```jsx
Methode : GET
https://queue.fal.run/fal-ai/veo3/requests/{{ $json.request_id }}
```

# 🔗 Link : [Blotato](https://blotato.com/?ref=firas)

# Support

[Get Support | Blotato Help](https://help.blotato.com/support/get-support)

# configuration :

```jsx
{
  "instagram_id": "111",
  "youtube_id": "222",
  "tiktok_id": "333",
  "facebook_id": "444",
  "facebook_page_id": "555",
  "threads_id": "666",
  "twitter_id": "777",
  "linkedin_id": "888",
  "pinterest_id": "999",
  "pinterest_board_id": "101010",
  "bluesky_id": "111111"
}

```

# **Blotato API Key**

[API keys | Blotato Help](https://help.blotato.com/settings/api-keys#blotato-api-key)

# **Upload Media /v2/media**

[Upload Media /v2/media | Blotato Help](https://help.blotato.com/api-reference/upload-media-v2-media#id-1.-upload-media)

```jsx
https://backend.blotato.com/v2/media

blotato-api-key
```

# **Social Platform Requirements**

[Social Platform Requirements | Blotato Help](https://help.blotato.com/tips-and-tricks/social-platform-requirements)

# **Social ALL CONFIG**

[Publish Post /v2/posts | Blotato Help](https://help.blotato.com/api-reference/publish-post-v2-posts)

# INSTAGRAM blotato config I

```jsx
https://backend.blotato.com/v2/posts
```

# INSTAGRAM blotato config II

[Publish Post /v2/posts | Blotato Help](https://help.blotato.com/api-reference/publish-post-v2-posts)

```jsx
{
  "post": {
    "accountId": "{{ $('Set Blotato ID').item.json.instagram_id }}",
    "target": {
      "targetType": "instagram"
    },
    "content": {
      "text": "{{ $('Google Sheets').item.json.DESCRIPTION }}",
      "platform": "instagram",
      "mediaUrls": [
        "{{ $json.url }}"
      ]
    }
  }
}

```

# YOUTUBE blotato config

```jsx
{
  "post": {
    "accountId": "{{ $('Set Blotato ID').item.json.youtube_id }}",
    "target": {
      "targetType": "youtube",
      "title": "{{ $('Google Sheets').item.json.Titre }}",
      "privacyStatus": "unlisted",
      "shouldNotifySubscribers": "false"
    },
    "content": {
      "text": "{{ $('Google Sheets').item.json.DESCRIPTION }}",
      "platform": "youtube",
      "mediaUrls": [
        "{{ $json.url }}"
      ]
    }
  }
}

```

# TIKTOK blotato config

```jsx
{
  "post": {
    "accountId": "{{ $('Set Blotato ID').item.json.tiktok_id }}",
    "target": {
      "targetType": "tiktok",
      "isYourBrand": "false", 
      "disabledDuet": "false",
      "privacyLevel": "PUBLIC_TO_EVERYONE",
      "isAiGenerated": "true",
      "disabledStitch": "false",
      "disabledComments": "false",
      "isBrandedContent": "false"
      
    },
    "content": {
      "text": "{{ $('Google Sheets').item.json.DESCRIPTION }}",
      "platform": "tiktok",
      "mediaUrls": [
        "{{ $json.url }}"
      ]
    }
  }
}

```

# FACEBOOK blotato config

```jsx
{
  "post": {
    "accountId": "{{ $('Assign Social Media IDs').item.json.facebook_id }}",
    "target": {
      "targetType": "facebook",
      "pageId": "{{ $('Assign Social Media IDs').item.json.facebook_page_id }}"

      
    },
    "content": {
      "text": "{{ $('Save Video Metadata to Google Sheets').item.json.DESCRIPTION }}",
      "platform": "facebook",
      "mediaUrls": [
        "{{ $json.url }}"
      ]
    }
  }
}
```

# THREADS blotato config

```jsx
{
  "post": {
    "accountId": "{{ $('Set Blotato ID').item.json.facebook_id }}",
    "target": {
      "targetType": "threads"
      
    },
    "content": {
      "text": "{{ $('Google Sheets').item.json.DESCRIPTION }}",
      "platform": "threads",
      "mediaUrls": [
        "{{ $json.url }}"
      ]
    }
  }
}

```

# TWITTER blotato config

```jsx
{
  "post": {
    "accountId": "{{ $('Set Blotato ID').item.json.facebook_id }}",
    "target": {
      "targetType": "twitter"
      
    },
    "content": {
      "text": "{{ $('Google Sheets').item.json.DESCRIPTION }}",
      "platform": "twitter",
      "mediaUrls": [
        "{{ $json.url }}"
      ]
    }
  }
}

```

# LINKEDIN blotato config

```jsx
{
  "post": {
    "accountId": "{{ $('Set Blotato ID').item.json.facebook_id }}",
    "target": {
      "targetType": "linkedin"
      
    },
    "content": {
      "text": "{{ $('Google Sheets').item.json.DESCRIPTION }}",
      "platform": "linkedin",
      "mediaUrls": [
        "{{ $json.url }}"
      ]
    }
  }
}

```

# BLUESKY blotato config

```jsx
{
  "post": {
    "accountId": "{{ $('Set Blotato ID').item.json.bluesky_id }}",
    "target": {
      "targetType": "bluesky"
      
    },
    "content": {
      "text": "{{ $('Google Sheets').item.json.DESCRIPTION }}",
      "platform": "bluesky",
      "mediaUrls": [
        "https://pbs.twimg.com/media/GE8MgIiWEAAfsK3.jpg"
      ]
    }
  }
}

```

# PINTEREST blotato config

```jsx
{
  "post": {
    "accountId": "{{ $('Set Blotato ID').item.json.pinterest_id }}",
    "target": {
      "targetType": "pinterest",
      "boardId": "{{ $('Set Blotato ID').item.json.pinterest_board_id }}"      
    },
    "content": {
      "text": "{{ $('Google Sheets').item.json.DESCRIPTION }}",
      "platform": "pinterest",
      "mediaUrls": [
        "https://pbs.twimg.com/media/GE8MgIiWEAAfsK3.jpg"
      ]
    }
  }
}

```

# PINTREST boardId / FILTRE BY . BoardsResource

```jsx
Find the board ID of this pinterest board based from this Network response:
The board ID has a format similar to this one: 1017321072016836595
```
