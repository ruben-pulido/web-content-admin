title: Web Content Administration
author:
  name: Rubén Pulido
style: basic-style.css
output: index.html
controls: false

--
# Web Content Administration

--
### Setup
- Create "My Masterclass" site based on "Masterclass" site template
- Update "Teacher" Web Content Template to display "info" field

```code
<h1>${Name.getData()}</h1>

<h3>
<#if (Info.getData())??>
	${Info.getData()}
</#if>
</h3>
```
--
### Web Content Administration (I)
- Edit
- Preview
- Translate
- Expire
- Subscribe
- View History
- View Usages
--
### Web Content Administration (II)
- Copy
- Export for Translation
- Import Translation
- Move
- Permissions
--
### View History
- Publish several versions of a Web Content (1.1, 1.2, 1.3) updating Teachers > Ralph Edwards
- View history (4 entries)
- Preview last version
- Preview second to last version
- Compare last two versions
- Copy second to last version*
- View history of the newly created web content and assert that it only has one version (version numbering starts all over from 1.0) 
--
### View History (Feedback*)

We show source ID and "Autogenerate ID" for the new ID but we don't allow overwriting the new ID field. 
- What is the purpose of this dialog? 
- Why do we have this dialog when copying a version of a Web Content and not when copying a Web Content?

--
### View Usages
- Create content page
- Add a "Content Display Element" fragment and map it to created web content
- Add a "Web Content Display" widget and map it to created web content
- Publish the page
- Copy the page
- View Usages of Web Content now displays 8 Usages

--
### View Usages (Feedback)
- Shouldn't it display 6 usages, since the new page that was created through the copy action hasn't been published yet?
- Should we add a column that allows identifying the name/url of the page/page template/master that is using the Web Content?
--
### Expire
- View History
- Expire last version
- Refresh page and assert that second to last version of the Web Content is now displayed on the page ->
Expire on the Web Content expires ALL versions of the web content
- Expire the Web Content entry
- Refresh the page and assert that no content is displayed now
--
### Expire (Feedback) 
It seems the "Expire" action cannot be undone. Should we add some kind of warning before expiring a version / a whole Web Content?
--
### Subscribe
- Create a new user: test2
- Assign it administration role
- With user test subscribe to WC "Teachers > Jerome Bell"
- With user test2 update WC info field to "1.1 Lorem"
- Assert user test gets a notification
- With user test unsubscribe from Web Content
- With user test2 update the Web Content info field to "1.2 Lorem"
- Assert user test no longer gets a notification
--
### Translate
- Translate Web Content: "Teachers > Jerome Bell"
- Change language to Spanish
- Set Info field to "1.2 Lorem es"
- Publish
--
### Export for translation
- Export for translation Web Content: "Teachers > Jerome Bell"
- Unzip file
- Open file on editor ~/Downloads/Jerome\ Bell-en_US-es_ES.xlf
- Update field:
```
		<unit id="DDMStructure_Info">
			<segment>
				<source><![CDATA[1.3 Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.]]></source>
				<target><![CDATA[1.3 Lorem es es]]></target>
			</segment>
		</unit>
```
--
### Import translation
- Import Translation for Web Content: "Teachers > Jerome Bell"
- Select file "~/Downloads/Jerome\ Bell-en_US-es_ES.xlf"
- Publish
- Click Done
- Open file on editor
- Click Translate
- Select Spanish
- Assert new value "1.3 Lorem es es" is present
--
### Documentation
**Managing Expired and Future Scheduled Web Content**

https://help.liferay.com/hc/en-us/articles/360018420931-Managing-Expired-and-Future-Scheduled-Web-Content

--
### Thank you!
<img 
  src="./images/thank-you.png" 
  alt="Thank you" 
  style="margin-left:auto;margin-right:auto;display:block;max-height:470px;max-width:800px;height:auto;width:auto;" />
--
