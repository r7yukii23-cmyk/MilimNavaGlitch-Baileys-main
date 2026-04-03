
<div align="center">
  <h1>MILIMNAVA BAILEYS</h1>
  <img src="https://upld.zone.id/uploads/4xiq6f1iq/1001594456.webp" alt="Thumbnail" width='100%' />
</div>

<br>

The latest updated Baileys WhatsApp supports following channels, and doesn't exit easily when using WhatsApp or Telegram bots. This Baileys is equipped with the latest buttons and has updated the jid to lid, suitable for those of you who have a project. Please use this Baileys. 

WhatsApp Baileys updates the jid to lid, payment/interactiveMessage/viewOnceMessage buttons and others, suitable for those of you who have a script project that you want 

---

### Features improved by the owner

- Already supports custom pairing code 
- Fixing damage to Pairing 
- Supports Paymess, Interactive, and button
- Support button in WhatsApp business  
- Faster performance

## Add Function ( Simple code )

### Label Group
Tag/Label Member Grop

```javascript
await milimnava.setLabelGroup(jid, string)
```
---
### Delay
Sleep code ( hehe )

```javascript
await milimnava.delay(seconds) // ex. 3 ( 3 seconds )
// example
await milimnava.delay(3)
```
---
### React Message
Send Reaction into the Message

```javascript
await milimnava.react(m, emoji) 
// Example 
await milimnava.react(m, "😚") 
```
---
### Delete React Message
Delete Reaction into the Message

```javascript
// Example 
await milimnava.unreact(m) 
```
---
### Check ID Channel / Newsletter / Saluran
Get ID Channel From Url

```javascript
await milimnava.cekIDSaluran(url)
```
Result JSON
```json
{
  "name": "Name Channel",
  "id": "Channel ID",
  "state": "Status Channel",
  "subscribers": "Followers",
  "verification": "UNVERIFIED",
  "creation_time": 1728547155,
  "description": "Description Channel"
  // ...etc
}
```
---
### Multiple Follow Newsletter
Just one line, not use array, just string with space " "

```javascript
await milimnava.newsletterMultipleFollow(jids)
// Example
await milimnava.newsletterMultipleFollow("120xxxxxxx@newsletter 120xxxxxxxxx@newsletter 120xxxxxxx@newsletter")
```
---
### Check banned number
You can see the status of blocked numbers here 

```javascript
milimnava.checkBanned(jid)
```
---
### Edit Message
Edit your previously sent message
```js
await milimnava.edit(m, newText)
// Example
await milimnava.edit(m, "this is edited message")
```
Notes
- Only works for messages sent by yourself
- Supports private chat, group, and newsletter
---
### Delete / Revoke Message
Delete or revoke a message
```js
await milimnava.del(m)
// Example
await milimnava.del(m)
```

Notes
- Private chat: revoke message
- Group chat:
- - Your message -> revoke for everyone
- - Other message -> delete for me
---
### Detect Message
Detect message type from incoming message object.
```js
milimnava.detect(m)
// Example
const type = ourin.detect(m)
if (type === 'image') {
    // handle image message
}
```
**Returned Type**
- text
- image
- video
- gif
- audio
- ptt
- sticker
- document
- reaction
- viewonce
- edited
- revoke
- interactive
- poll
- location
- contact
- Unknown

**Notes**
- Automatically normalizes message content
- Safe for plugins and middleware
- Avoid deep manual message checks
- Stable across Baileys updates
---
# SendMessage Documentation

### Send Status Mention
Status Mention Group & Private Message
Send Status Mention Group/Private Chat

```javascript
await milimnava.sendStatusMention(content, jid);
```

### Status Group Message V2
Send Group Status With Version 2 

```javascript
await milimnava.sendMessage(jid, {
     groupStatusMessage: {
          text: "Hello World"
     }
});
```

### Album Message (Multiple Images)
Send multiple images in a single album message:

```javascript
await milimnava.sendMessage(jid, { 
    albumMessage: [
        { image: buffer, caption: "Foto pertama" },
        { image: { url: "URL IMAGE" }, caption: "Foto kedua" }
    ] 
}, { quoted: m });
```

### Event Message
Create and send WhatsApp event invitations:

```javascript
await milimnava.sendMessage(jid, { 
    eventMessage: { 
        isCanceled: false, 
        name: "Hello World", 
        description: "yuedev", 
        location: { 
            degreesLatitude: 0, 
            degreesLongitude: 0, 
            name: "milimnava" 
        }, 
        joinLink: "https://call.whatsapp.com/video/saweitt", 
        startTime: "1763019000", 
        endTime: "1763026200", 
        extraGuestsAllowed: false 
    } 
}, { quoted: m });
```

### Poll Result Message
Display poll results with vote counts:

```javascript
await milimnava.sendMessage(jid, { 
    pollResultMessage: { 
        name: "Hello World", 
        pollVotes: [
            {
                optionName: "TEST 1",
                optionVoteCount: "112233"
            },
            {
                optionName: "TEST 2",
                optionVoteCount: "1"
            }
        ] 
    } 
}, { quoted: m });
```

### Simple Interactive Message
Send basic interactive messages with copy button functionality:

```javascript
await milimnava.sendMessage(jid, {
    interactiveMessage: {
        header: "Hello World",
        title: "Hello World",
        footer: "MILIMNAVA",
        buttons: [
            {
                name: "cta_copy",
                buttonParamsJson: JSON.stringify({
                    display_text: "copy code",
                    id: "123456789",              
                    copy_code: "ABC123XYZ"
                })
            }
        ]
    }
}, { quoted: m });
```

### Interactive Message with Native Flow
Send interactive messages with buttons, copy actions, and native flow features:

```javascript
await milimnava.sendMessage(jid, {    
    interactiveMessage: {      
        header: "Hello World",
        title: "Hello World",      
        footer: "MILIMNAVA",      
        image: { url: "https://example.com/image.jpg" },      
        nativeFlowMessage: {        
            messageParamsJson: JSON.stringify({          
                limited_time_offer: {            
                    text: "idk hummmm?",            
                    url: "https://milimnava.site",            
                    copy_code: "yuedev",            
                    expiration_time: Date.now() * 999          
                },          
                bottom_sheet: {            
                    in_thread_buttons_limit: 2,            
                    divider_indices: [1, 2, 3, 4, 5, 999],            
                    list_title: "yuedev",            
                    button_title: "yuedev"          
                },          
                tap_target_configuration: {            
                    title: " X ",            
                    description: "bomboclard",            
                    canonical_url: "https://milimnava.site",            
                    domain: "shop.example.com",            
                    button_index: 0          
                }        
            }),        
            buttons: [          
                {            
                    name: "single_select",            
                    buttonParamsJson: JSON.stringify({              
                        has_multiple_buttons: true            
                    })          
                },          
                {            
                    name: "call_permission_request",            
                    buttonParamsJson: JSON.stringify({              
                        has_multiple_buttons: true            
                    })          
                },          
                {            
                    name: "single_select",            
                    buttonParamsJson: JSON.stringify({              
                        title: "Hello World",              
                        sections: [                
                            {                  
                                title: "title",                  
                                highlight_label: "label",                  
                                rows: [                    
                                    {                      
                                        title: "@saweitt",                      
                                        description: "love you",                      
                                        id: "row_2"                    
                                    }                  
                                ]                
                            }              
                        ],              
                        has_multiple_buttons: true            
                    })          
                },          
                {            
                    name: "cta_copy",            
                    buttonParamsJson: JSON.stringify({              
                        display_text: "copy code",              
                        id: "123456789",              
                        copy_code: "ABC123XYZ"            
                    })          
                }        
            ]      
        }    
    }  
}, { quoted: m });
```

### Interactive Message with Thumbnail
Send interactive messages with thumbnail image and copy button:

```javascript
await milimnava.sendMessage(jid, {
    interactiveMessage: {
        header: "Hello World",
        title: "Hello World",
        footer: "MILIMNAVA",
        image: { url: "https://example.com/image.jpg" },
        buttons: [
            {
                name: "cta_copy",
                buttonParamsJson: JSON.stringify({
                    display_text: "copy code",
                    id: "123456789",
                    copy_code: "ABC123XYZ"
                })
            }
        ]
    }
}, { quoted: m });
```

### Product Message
Send product catalog messages with buttons and merchant information:

```javascript
await milimnava.sendMessage(jid, {
    productMessage: {
        title: "Produk Contoh",
        description: "Ini adalah deskripsi produk",
        thumbnail: { url: "https://example.com/image.jpg" },
        productId: "PROD001",
        retailerId: "RETAIL001",
        url: "https://example.com/product",
        body: "Detail produk",
        footer: "Harga spesial",
        priceAmount1000: 50000,
        currencyCode: "USD",
        buttons: [
            {
                name: "cta_url",
                buttonParamsJson: JSON.stringify({
                    display_text: "Beli Sekarang",
                    url: "https://example.com/buy"
                })
            }
        ]
    }
}, { quoted: m });
```

### Interactive Message with Document Buffer
Send interactive messages with document from buffer (file system) - **Note: Documents only support buffer**:

```javascript
await milimnava.sendMessage(jid, {
    interactiveMessage: {
        header: "Hello World",
        title: "Hello World",
        footer: "MILIMNAVA",
        document: fs.readFileSync("./package.json"),
        mimetype: "application/pdf",
        fileName: "saweitt.pdf",
        jpegThumbnail: fs.readFileSync("./document.jpeg"),
        contextInfo: {
            mentionedJid: [jid],
            forwardingScore: 777,
            isForwarded: false
        },
        externalAdReply: {
            title: "MILIMNAVA",
            body: "Yue",
            mediaType: 3,
            thumbnailUrl: "https://example.com/image.jpg",
            mediaUrl: " X ",
            sourceUrl: "https://milimnava.site",
            showAdAttribution: true,
            renderLargerThumbnail: false         
        },
        buttons: [
            {
                name: "cta_url",
                buttonParamsJson: JSON.stringify({
                    display_text: "Telegram",
                    url: "https://milimnava.site",
                    merchant_url: "https://milimnava.site"
                })
            }
        ]
    }
}, { quoted: m });
```

### Interactive Message with Document Buffer (Simple)
Send interactive messages with document from buffer (file system) without contextInfo and externalAdReply - **Note: Documents only support buffer**:

```javascript
await milimnava.sendMessage(jid, {
    interactiveMessage: {
        header: "Hello World",
        title: "Hello World",
        footer: "MILIMNAVA",
        document: fs.readFileSync("./package.json"),
        mimetype: "application/pdf",
        fileName: "saweitt.pdf",
        jpegThumbnail: fs.readFileSync("./document.jpeg"),
        buttons: [
            {
                name: "cta_url",
                buttonParamsJson: JSON.stringify({
                    display_text: "Telegram",
                    url: "https://milimnava.site",
                    merchant_url: "https://milimnava.site"
                })
            }
        ]
    }
}, { quoted: m });
```

### Request Payment Message
Send payment request messages with custom background and sticker:

```javascript
let quotedType = m.quoted?.mtype || '';
let quotedContent = JSON.stringify({ [quotedType]: m.quoted }, null, 2);

await milimnava.sendMessage(jid, {
    requestPaymentMessage: {
        currency: "IDR",
        amount: 10000000,
        from: m.sender,
        sticker: JSON.parse(quotedContent),
        background: {
            id: "100",
            fileLength: "0",
            width: 1000,
            height: 1000,
            mimetype: "image/webp",
            placeholderArgb: 0xFF00FFFF,
            textArgb: 0xFFFFFFFF,     
            subtextArgb: 0xFFAA00FF   
        }
    }
}, { quoted: m });
```

### Carousel Message
Send a carousel message with multiple cards:

```javascript
await milimnava.sendMessage(
    jid,
    {
        text: 'Body Message',
        title: 'Title Message', 
        subtile: 'Subtitle Message', 
        footer: 'Footer Message',
        cards: [
           {
              image: { url: 'https://example.com/jdbenkksjs.jpg' }, // or buffer
              title: 'Title Cards',
              body: 'Body Cards',
              footer: 'Footer Cards',
              buttons: [
                  {
                      name: 'quick_reply',
                      buttonParamsJson: JSON.stringify({
                         display_text: 'Display Button',
                         id: 'ID'
                      })
                  },
                  {
                      name: 'cta_url',
                      buttonParamsJson: JSON.stringify({
                         display_text: 'Display Button',
                         url: 'https://www.example.com'
                      })
                  }
              ]
           },
           {
              video: { url: 'https://example.com/jdbenkksjs.mp4' }, // or buffer
              title: 'Title Cards',
              body: 'Body Cards',
              footer: 'Footer Cards',
              buttons: [
                  {
                      name: 'quick_reply',
                      buttonParamsJson: JSON.stringify({
                         display_text: 'Display Button',
                         id: 'ID'
                      })
                  },
                  {
                      name: 'cta_url',
                      buttonParamsJson: JSON.stringify({
                         display_text: 'Display Button',
                         url: 'https://www.example.com'
                      })
                  }
              ]
           }
        ]
    }
)
```

### Sticker Pack Message
Send a sticker pack with multiple stickers in one message:

```javascript
await milimnava.sendMessage(jid, {
    stickerPack: {
        name: "My Sticker Pack",
        publisher: "MILIMNAVA",
        description: "Custom sticker pack",
        cover: { url: "https://example.com/cover.png" },
        stickers: [
            { sticker: fs.readFileSync("./sticker1.webp"), emojis: ["😎"] },
            { sticker: fs.readFileSync("./sticker2.webp"), isAnimated: true },
            { sticker: { url: "https://example.com/sticker3.webp" } }
        ]
    }
}, { quoted: m });
```

**Sticker Options**
- `sticker` — Buffer or URL of the sticker (WebP format)
- `emojis` — Array of emoji associated with the sticker
- `isAnimated` — Set to `true` for animated stickers
- `isLottie` — Set to `true` for Lottie stickers
- `accessibilityLabel` — Accessibility label for the sticker

---

## Media Utilities

Lightweight media processing functions built directly into the socket. Uses `sharp` (native C) for images and `ffmpeg` pipes for video/audio — zero temp files, maximum speed.

### Resize
Fast image resize with aspect ratio preserved

```javascript
const resized = await milimnava.resize(buffer, 200, 200)
```
---
### Convert
Convert media format — supports `jpeg`, `jpg`, `png`, `webp`, `mp3`, `mp4`

```javascript
const mp4 = await milimnava.convert(buffer, { to: "mp4" })
const webp = await milimnava.convert(buffer, { to: "webp" })
const mp3 = await milimnava.convert(buffer, { to: "mp3" })
```
---
### To Sticker
Convert any image to WhatsApp sticker format (512x512 WebP with transparency)

```javascript
const sticker = await milimnava.toSticker(buffer)
const sticker = await milimnava.toSticker(buffer, { quality: 90 })
```
---
### Compress
Compress media with quality control — auto-detects image or video

```javascript
const compressed = await milimnava.compress(buffer, { quality: 50 })
```
---
### Metadata
Extract media metadata — auto-detects image (sharp) or video/audio (ffprobe)

```javascript
const info = await milimnava.metadata(buffer)
```

Result JSON
```json
{
  "size": 102400,
  "mimetype": "image/jpeg",
  "width": 1920,
  "height": 1080,
  "channels": 3,
  "hasAlpha": false
}
```

For video/audio:
```json
{
  "size": 5242880,
  "mimetype": "video/mp4",
  "width": 1280,
  "height": 720,
  "duration": 30.5
}
```

---

## Why Choose WhatsApp Baileys?

Because this library offers high stability, full features, and an actively improved pairing process. It is ideal for developers aiming to create professional and secure WhatsApp automation solutions. Support for the latest WhatsApp features ensures compatibility with platform updates.

---

For complete documentation, installation guides, and implementation examples, please visit the official repository and community forums. We continually update and improve this library to meet the needs of developers and users of modern WhatsApp automation solutions.

**Thank you for choosing WhatsApp Baileys as your WhatsApp automation solution!**