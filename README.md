# drupal-meeting-parser
This is a bare bones Google Chrome extension to copy Drupal Slack meeting threads to the system clipboard.

<img src="https://github.com/mdlutz24/drupal-meeting-parser/blob/master/icon.png" alt="Drupal Meeting Parser icon" align="right" />

Many Drupal teams use threaded meetings to discuss current topics. This
extension helps to archive the meeting log from these meetings for posterity.
Crediting meeting participants is facilitated as well.

## How to install

1. Enable developer mode for Google Chrome Extensions. 
   See https://developer.chrome.com/extensions/faq#faq-dev-01

2. Clone this repository to any location on your local computer.

3. Use the "Load unpacked" option under Chrome Extensions to add this
   unpacked Chrome Extension to your browser. Pick the directory you checked
   this out to.

4. A grayed out Drupal meeting parser icon will appear in your browser alongside
   the URL bar.

4. Open the chatroom in Google Chrome. The icon will become blue and four
   bright yellow buttons should apear on the top of the page: Clear memory, 
   Add with credit, Add without credit and To clipboard.

## When to use

It is advised not to save the meeting log right after the meeting as the format
itself allows remote participants to join slightly later. You should save the
meeting logs a day or so later when the meeting text is still available but
everybody had a chance to chime in.

## The four buttons

The extension injects four buttons at the top of every Slack page:

- **Clear memory** — wipes all accumulated threads so you can start fresh.
- **Add with credit** — captures the currently open thread and records its
  participants for the Participants list (see below).
- **Add without credit** — captures the thread text only; participants are
  *not* added to the Participants list. Use this for introductory or off-topic
  threads where credit is not appropriate.
- **Copy X threads to clipboard** — copies everything accumulated so far
  (all threads in the order you added them, plus the Participants list)
  to the OS clipboard, ready to paste.

## How to use

The extension accumulates threads in memory one at a time. You open each
thread, capture it, then move to the next. When you have captured all the
threads you want, you do a single paste into the Drupal.org meeting issue.

1. Open the first meeting thread in Slack by clicking its reply count.
   Wait for the thread panel to appear on the right side of the screen.

2. Click **Add with credit** (for substantive agenda threads) or
   **Add without credit** (for roll-call, intro, or off-topic threads).
   The button will show [Processing] while the extension scrolls through
   the thread to load all messages, then turn yellow again when done.

3. Open the next thread and click Add again. Repeat for every thread you
   want to include in the meeting notes.

4. When you have captured all threads, click **Copy X threads to clipboard**.
   Your meeting notes are now on the clipboard.

5. Go to the Drupal.org meeting issue node and paste. You will get:
   - An HTML table for each thread, formatted for the issue body.
   - A **Participants** section at the end listing everyone who spoke in
     threads you captured with credit.

6. Paste the Participants list into the **"Credit others"** field (inside
   the "Crediting & committing" fieldset at the bottom of the issue).
   This field is only visible to project maintainers. If you are not a
   maintainer, ask one to handle crediting.

**Note on usernames:** Drupal.org usernames are not always the same as Slack
display names. After pasting, check which users received credits and manually
add the correct Drupal.org usernames for anyone who was missed. Some common
mappings are built into the extension. More can be added — please submit them
as issues at https://github.com/mdlutz24/drupal-meeting-parser/issues.

Finally, don't forget to close the issue as fixed so the credits will be
granted.

## Contributing

All aspects of the extension can be improved, contributions welcome.
