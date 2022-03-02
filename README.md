# telegram-chat-verifier
Service to verify suspicious Telegram chats

## Ideas/Requirements
### Flow
1. Simple web page with text field to provide a link to telegram chat
2. Provided link is normalizad (strip spaces, etc) and check agains existing ones, once exists - ignore
3. Link is added to DB with `UNVERIFIED` status
4. Verification job takes unverified links and validate chat content against predefined text patterns
    1. In case patterns were found - mark it as `AUTOMATIC_SUSPICIOUS`
    2. In case of no patterns found - mark as `AUTOMATIC_SAFE`
5. All suspicious links to be posted in predefined (public) telegram chat in order to verify/react by volunteers
    1. Any way to provide feedback from chat above? 

### Security
* Block russia by GeoIP
* Block IPs with high input rate (automatic scripts)
