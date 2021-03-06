Changes in MatrixKit in 0.4.11 (2017-03-23)
==========================================

Improvements:
 * Upgrade MatrixSDK version (v0.7.11).
 
Bug fixes:
 * Chat screen: image thumbnails management is broken (https://github.com/vector-im/riot-ios#1121).
 * Image viewer repeatedly loses overlay menu (https://github.com/vector-im/riot-ios#1109).

Changes in MatrixKit in 0.4.10 (2017-03-21)
==========================================

Improvements:
 * Upgrade MatrixSDK version (v0.7.10).

Changes in MatrixKit in 0.4.9 (2017-03-16)
==========================================

Improvements:
 * Upgrade MatrixSDK version (v0.7.9).
 
Bug fixes:
 * Riot user created without msisdn in his settings (https://github.com/vector-im/riot-ios#1103).

Changes in MatrixKit in 0.4.8 (2017-03-10)
==========================================

Improvements:
 * Upgrade MatrixSDK version (v0.7.8).
 * MXKRoomActivitiesView: Manage room activities view height changes.
 * Crypto - Warn unknown devices: treat MXDeviceUnknown as MXDeviceUnverified.
 * Crypto: Add MXKEncryptionInfoViewDelegate to be notified when the device has been verified.
 * Crypto: Reset devices keys when clearing app cache in order to fix UISIs received by other people.
 * Add MXKCountryPickerViewController.
 * MXKContactManager: Reload the local contacts from the system when the user changes his mind and disables the contact sync.
 * MXKAccount: List the phone numbers linked to the account.
 * MXKAccount: add warnedAboutEncryption property.
 * MXK3PID: Support phone number validation.
 * CommonMark: Replace GHMarkdownParser with cmark.
 * MXKAuthInputsPasswordBasedView: Suport the new Login API with different types of identifiers.
 * MXKContactManager: Discover matrix users by using the local phonebook entries (email and phone number) (https://github.com/vector-im/riot-ios#904).
 
Bug fixes:
 * Self-signed homeserver: Moved the code that trusts already trusted certificate into MXRestClient (Related to https://github.com/matrix-org/matrix-ios-sdk/pull/248).
 * MXKAuthenticationViewController: Fix notification loop on server error.
 
API breaks:
  * MXKAuthInputsViewDelegate: [authInputsViewEmailValidationRestClient:] has been renamed to [authInputsViewThirdPartyIdValidationRestClient:].
  * MXKDeviceView: [deviceViewDidUpdate:] has been renamed to [dismissDeviceView: didUpdate:].

Changes in MatrixKit in 0.4.7 (2017-02-08)
==========================================

Improvements:
 * Upgrade MatrixSDK version (v0.7.7).
 * Add E2E keys export & import. This is managed by new MXKEncryptionKeysImportView and MXKEncryptionKeysExportView views.
 * Show riot enabled local contacts in known contacts too (https://github.com/vector-im/riot-ios#1001).
 
Bug fixes:
 * Duplicated msg when going into room details (https://github.com/vector-im/riot-ios#970).
 * Local echoes for typed messages stay (far) longer in grey (https://github.com/vector-im/riot-ios#1007).
 * Should fix crash in 0.3.8: [MXKRoomInputToolbarView contentEditingInputsForAssets:withResult:onComplete:] (https://github.com/vector-im/riot-ios#1015).
 
Changes in MatrixKit in 0.4.6 (2017-01-24)
==========================================

Improvements:
 * Upgrade MatrixSDK version (v0.7.6).
 * MXKContactManager: Support bulk lookup to discover the matrix users in local contacts.
 * MXKContactTableCell: Let contacts table refresh matrix ids of the local contacts.
 
Bug fixes:
 * Bug Fix: App is stuck on logout when device is offline (https://github.com/vector-im/riot-ios#963).

Changes in MatrixKit in 0.4.5 (2017-01-19)
==========================================

Improvements:
 * Upgrade MatrixSDK version (v0.7.5).
 * View controller: Remove properties initialization from `viewDidLoad` (#94)
 * MXKContact: Add [initContactWithDisplayName:emails:phoneNumbers:andThumbnail:] method.
 * MXKContactManager: Add API to sort a contacts array.
 * MXKContactManager: Add `localContactsSplittedbyContactMethod` property, the contacts list obtained by splitting each local contact by contact method.
 
Bug fixes:
 * Cloned rooms in rooms list (vector-im/riot-ios#889).
 * Riot looks to me like I'm sending the same message twice (vector-im/riot-ios#894).
 * matrix.to links containing room ids are not hyperlinked (vector-im/riot-ios#886).
 * Integer negative wraparound in upload progress meter (vector-im/riot-ios#892).
 * MXKRoomBubbleTableViewCell: a square avatar has been observed.
 * MXKContact: Encode the thumbnail of the local contacts.

API breaks:
 * MXKContactManager: Replace `localEmailContacts:` with `localContactsWithMethods:` to list the local contacts who have contact methods which may be used to invite them or to discover matrix users.

Changes in MatrixKit in 0.4.4 (2016-12-23)
==========================================

Improvements:
 * Upgrade MatrixSDK version (v0.7.4).
 * Crypto: add MXKDeviceView and MXKEncryptionInfoView to display device or encryption information.
 * Crypto: Improve decryption error messages (specially for unknown inbound session id).
 * MXKEventFormatter: add encryptingTextColor settings property.
 
Bug fixes:
 * Voip : decline call when room opened freeze riot (https://github.com/vector-im/vector-ios#764).

API breaks:
 * MXKCallViewController: remove `isPresented` property.
 * Move MXKMediaManager and MXKMediaLoader at SDK level.
 * Move MXEncryptedAttachments to SDK level.
 * Move outgoing messages management to SDK level.

Changes in MatrixKit in 0.4.3 (2016-11-23)
===========================================

Improvements:
 * Upgrade MatrixSDK version (v0.7.3).
 
Bug fixes:
 * Typing indicator should stop when the user sends his message (https://github.com/vector-im/vector-ios#809).
 * Crypto: Made attachments work better cross platform.

Changes in MatrixKit in 0.4.2 (2016-11-22)
===========================================

Improvements:
 * Upgrade MatrixSDK version (v0.7.2).
 * MXKAccount: Add API to handle account device information.
 
Bug fixes:
 * Crypto: Do not allow to redact the event that enabled encryption in a room.

Changes in MatrixKit in 0.4.1 (2016-11-18)
===========================================

Improvements:
 * Upgrade MatrixSDK version (v0.7.1).
 
Bug fixes:
 * Make share/save/copy work for e2e attachments.
 * Fix a random crash when uploading an e2e attachment.
 * Wrong thumbnail shown whilst uploading e2e image  (https://github.com/vector-im/vector-ios#795).

Changes in MatrixKit in 0.4.0 (2016-11-17)
===========================================

Improvements:
 * Upgrade MatrixSDK version (v0.7.0).
 * Support end-to-end encryption.
 * Chat history: Display a message for `m.room.encryption` events.
 * MXKAccount: Logout properly by invalidating the access token.
 * Tag explicitly the invite as DM or not DM (https://github.com/vector-im/vector-ios/issues/714).
 * MXKRecentListViewController: Reload the table view on the direct rooms update (https://github.com/vector-im/vector-ios/issues/715).
 * MXKAttachment: Generate thumbnail URL.
 * MXKRoomDataSource: Create and upload thumbnails for encrypted images.
 
 API break:
 * MXKEventFormatter: remove `fakeRoomMessageEventForRoomId` API (temporary events are now created by MXRoom class).
 
 Bug fixes:
 * Use `contains_url` filter during the attachments search (https://github.com/vector-im/vector-ios/issues/652).
 * MXKRoomDataSource: infinite loop on empty bubbles array.
 * MXKRoomInputToolbarView: Disable view animation during text reset to prevent placeholder distorsion.
 * Fix for accepting autocorrect on message send.
 * MXKRoomBubbleCellData: Should fix the text bubbles overlapping.

Changes in MatrixKit in 0.3.19 (2016-09-30)
===========================================
 
 Bug fixes:
 * App crashes when user taps on room alias with multiple # in chat history (https://github.com/vector-im/vector-ios/issues/668).
 * Room message search: the search pattern is not highlighted in results (https://github.com/vector-im/vector-ios/issues/660).

Changes in MatrixKit in 0.3.18 (2016-09-27)
===========================================

Improvements:
 * Upgrade MatrixSDK version (v0.6.17).
 * MXKCallViewController: Hide camera switch on voice call.
 
 Bug fixes:
 * No ringback tones when placing voice calls in silent mode (https://github.com/vector-im/vector-ios/issues/631).
 * Going back into a VC from back-to-app takes the call off speakerphone (https://github.com/vector-im/vector-ios/issues/581).
 * Transparent png avatars are shown on black rather than white bg when RRs (https://github.com/vector-im/vector-ios/issues/639).
 * iOS cannot play videos sent from web (https://github.com/vector-im/vector-ios/issues/640).
 * MXKPieChartView: The background view is not reset on background color (unprogressColor) change.
 * MXKEventFormatter: The invitation rejection was not displayed.
 * The room preview does not always display the right member info (https://github.com/vector-im/vector-ios/issues/643).

Changes in MatrixKit in 0.3.17 (2016-09-15)
===========================================

Improvements:
 * Upgrade MatrixSDK version (v0.6.16).
 * MXKCallViewController: For 1:1 call, display the other peer information instead of the room information.
 
 Bug fixes:
 * Chat screen: unexpected scroll up on new sent messages (https://github.com/vector-im/vector-ios/issues/600).

Changes in MatrixKit in 0.3.16 (2016-09-08)
===========================================

Improvements:
 * Upgrade MatrixSDK version (v0.6.14).
 * Hyperlink mxids and room aliases  (https://github.com/vector-im/vector-ios/issues/442).
 * Handle 404 (Event not found) on permalinks (https://github.com/vector-im/vector-ios/issues/484).
 * MXKRoomDataSourceManager: Add API to mark all messages as read (https://github.com/vector-im/vector-ios/issues/442).
 * Chat screen: New message(s) notification (https://github.com/vector-im/vector-ios/issues/532).
 * MXKCallViewController: support custom audio sounds.
 * MXKRoomInputToolbarView: Expose the becomeFirstResponder method.
 * MXKRoomViewController: expose showEventDetails method.
 * MXKEventFormatted: Save 2 seconds on app startup when a last message is a HTLM code block.
 * MXKRoomDataSourceManager: Add missedHighlightDiscussionsCount method (https://github.com/vector-im/vector-ios/issues/563).
 * MXKContactManager: Expose the current list of the contacts for whom a 1:1 room exists (https://github.com/vector-im/vector-ios/issues/529).
 * MXKEventFormatter: Until e2e is impl'd, encrypted msgs should be shown in the UI as unencryptable warning text (https://github.com/vector-im/vector-ios/issues/559).
 * MXKEventFormatter: Change how the kick reason is displayed (https://github.com/vector-im/vector-ios/issues/549).

Bug fixes:
 * Room Settings: some addresses are missing (https://github.com/vector-im/vector-ios/issues/528).
 * Sync has got stuck while the app was backgrounded (https://github.com/vector-im/vector-ios/issues/506).
 * Chat screen: wrong attachment is opened (https://github.com/vector-im/vector-ios/issues/387).
 * Chat screen: mention the member name at the cursor position (not a the end) (https://github.com/vector-im/vector-ios/issues/issues/385).
 * Chat screen: Add feedback when user clicks on attached files (https://github.com/vector-im/vector-ios/issues/534).
 * MXKTableViewCellWithLabelAndTextField: Label is cropped when text field value is too long.
 * Attachment viewer: Video controls are buggy (https://github.com/vector-im/vector-ios/issues/460).
 * Preview on world readable room failed.  (https://github.com/vector-im/vector-ios/issues/556).
 * Vector automatically marks incoming messages as read in background (https://github.com/vector-im/vector-ios/issues/558).
 * Call Locking phone whilst setting up a call interrupts the call setup (https://github.com/vector-im/vector-ios/issues/161).

Changes in MatrixKit in 0.3.15 (2016-08-25)
===============================================

Bug fixes:
 * Fix crash in recents screen.

Changes in MatrixKit in 0.3.14 (2016-08-25)
===============================================

Improvements:
 * Upgrade MatrixSDK version (v0.6.13).
 * MXCallViewController: Add conference call support.
 * MXCallViewController: Add camera switch.
 * MXKRoomInputToolbarView: Manage sending of a multiselection of media (https://github.com/vector-im/vector-ios/301).
 * MXKRoomSettingsViewController: increase section header height.

Bug fixes:
 * Redacting membership events should immediately reset the displayname & avatar of room members (https://github.com/vector-im/vector-ios/issues/443).
 * Profile changes shouldn't reorder the room list (https://github.com/vector-im/vector-ios/issues/494).
 * When the last message is redacted, [MXKRecentCellData update] makes paginations loops (https://github.com/vector-im/vector-ios/issues/520).
 * Call: the remote and local video are not scaled to fill the video container (https://github.com/vector-im/vector-ios/issues/537).
 * Call: Screen still tries to turn off when on a VC (https://github.com/vector-im/vector-ios/issues/521).
 * Call: Do not vibrate when outgoing call is placed.
 * The message displayed in a room when a 3pid invited user has registered is not clear (https://github.com/vector-im/vector-ios/issues/74).
 
Changes in MatrixKit in 0.3.13 (2016-08-01)
===============================================

Improvements:
 * Upgrade MatrixSDK version (v0.6.12).
 * MXTools: Added methods to check media access permissions like Camera or Microphone.
 * MXCallViewController: Check permissions before accessing the microphone or the camera.

Bug fixes:
 * Vector is turning off my music now that VoIP is implemented (https://github.com/vector-im/vector-ios/476)
 
Changes in MatrixKit in 0.3.12 (2016-07-26)
===============================================

Improvements:
 * Upgrade MatrixSDK version (v0.6.11).

Bug fixes:
 * Confirmation prompt before opping someone to same power level (https://github.com/vector-im/vector-ios/issues/461).
 * Fixed string displayed on outgoing video call (it said "xxx placed a voice call)
 * Room Settings: The room privacy setting text doesn't fit in phone mode (https://github.com/vector-im/vector-ios/issues/429).

Changes in MatrixKit in 0.3.11 (2016-07-15)
===============================================

Improvements:
 * Upgrade MatrixSDK version (v0.6.10).
 * MXKRoomDataSource: Display room history visibility changes.
 * MXKEventFormatter: Add the defaultCSS property to enrich the defaultCSS used by DTCoreText.
 * MatrixKitTests: Create first MatrixKit unitary test.

Bug fixes:
 * Markdown swallows leading #'s even if there are less than 3 (https://github.com/vector-im/vector-ios/issues/423).
 * Fix the rendering of <code> tags: line breaks are kept, the Menlo font is used with a light grey background.
 * HTML blockquote is badly rendered: some characters can miss (https://github.com/vector-im/vector-ios/issues/437).
 * MXKRoomSettingsViewController: Infinite loading wheel on bad network.
 * MXKEventFormatter - Fix crash on NSConcreteMutableAttributedString initWithString:: nil value.

Changes in MatrixKit in 0.3.10 (2016-07-01)
===============================================

Improvements:
 * Upgrade MatrixSDK version (v0.6.9).
 * MXKRoomDataSource: Add the ability to peek into a room.
 * MXKRoomDataSource: Add Markdown typing support.
 * MXKRoomViewController: Use room peeking in room preview.
 * MXKRoomViewController: when opening a permalink, center the corresponding event on the screen.
 * MXKRoomViewController: Add missing slash commands: /invite, /part and /topic (https://github.com/vector-im/vector-ios/issues/223)
 * MXKRoomViewController: Expose [setAttachmentsViewerClass:].
 * MXKRoomViewController: Rename joinRoomWithRoomId to joinRoomWithRoomIdOrAlias.
 * MXKRecentListViewController: Add sanity check to prevent infinite loop.
 * MXKSearchViewController: Improved memory management.
 * MXKContact: add sorting display name definition.
 * MXKContact: Add hasPrefix method.
 * MXKEventFormatter: Support of display of "org.matrix.custom.html" formatted message body (#124).
 * MXKTableViewCellWithLabelAndSwitch: Update UISwitch constraints.

Bug fixes:
 * Room screen:  Tap on attached video does nothing (https://github.com/vector-im/vector-ios/issues/380)
 * Hitting back after search results does not refresh results (https://github.com/vector-im/vector-ios/issues/190)
 * App crashes on : [<__NSDictionaryM> valueForUndefinedKey:] this class is not key value coding-compliant for the key <redacted>.
 * MXKEventFormatter: Add sanity check on event content values to "-[__NSCFDictionary length]: unrecognized selector sent to instance"
 * MXKRoomActivitiesView: Fix exception on undefined MXKRoomActivitiesView.xib.
 * App freezes on iOS8 when user goes back on Recents from a Room Chat.
 * MXKTools: The unit of formatted seconds interval is 'ss' instead of 's'.
 * Room settings: refresh on room state change.
 * App crashes on '/join' command when no param is provided.

Changes in MatrixKit in 0.3.9 (2016-06-02)
===============================================

Bug fix:
 * Invitation preview button is broken.

Changes in MatrixKit in 0.3.8 (2016-06-01)
===============================================

Improvements:
 * Upgrade MatrixSDK version (v0.6.8).
 * MXKRoomDataSource: Display all call events (invite, answer, hangup).
 * MXKAuthenticationViewController: Expose [onFailureDuringAuthRequest:].
 * MXKAuthenticationViewController: Support "Forgot Password".
 * MXKRoomMemberListViewController: Expose scrollToTop method.
 * MXKAccount: logout when the access token is no more valid.
 * MXKAccount: Refresh pusher (if any) when the app is resumed.
 * MXKRoomViewController: Do nothing when clicking on an unsent media.
 * MXKTableViewCell: expose layout constraints.
 * MXKTableViewCell: Define display box types.
 * MXKWebViewViewController: Support local HTML file + Handle goBack option.
 * MXKRoomMemberDetailsViewController: Support 'Mention' option.
 * MXKRecentListViewController: Apply apple look&feel on overscroll.
 * MXKRoomDataSourceManager: add missed discussions count.
 * MXKSearchViewController: Handle correctly end of search.

Bug fixes:
 * Application can crash when a video failed to be converted before sending.
 * Loading one image thumbnail in a sequence seems to set all fullres images downloading.
 * It's too hard to press names to auto-insert nicks.
 * It sound like something is filling up the logs.
 * App crashes on room members.

Changes in MatrixKit in 0.3.7 (2016-05-04)
===============================================

Improvements:
 * Upgrade MatrixSDK version (v0.6.7).
 * MXKRecentTableViewCell: Support user's action on recent cell.
 * MXKTools: Add formatSecondsIntervalFloored (Format time interval but rounded to the nearest time unit below).
 * MXKTools: i18n'ed formatSecondsInterval methods.
 * MXKRoomBubbleTableViewCell: Support tap on sender name label
 * MXKRoomViewController: Insert sender name in text input by tapping on avatar or display name.
 * Ability to report abuse
 * Ability to ignore users

Bug fixes:
 * Handle the error on joining a room where everyone has left.
 * Video playback stops when you rotate the device.
 * Enable notifications on your device' toggle spills over the side on an iPhone 5 display.

Changes in MatrixKit in 0.3.6 (2016-04-26)
===============================================

Improvements:
 * Upgrade MatrixSDK version (v0.6.6).
 * MXKRoomViewController: Support room preview.
 * MXKRoomViewController: Added "joinRoomWithRoomId:andSignUrl:" to join a room from a 3PID invitation.
 * MXKRoomViewController: input tool bar and activities view may be removed on demand.
 * MXKCellRenderingDelegate: Added shouldDoAction delegate operation (a mechanism to ask the app if a link can be opened automatically by the system).
 * Media Picker - Video playback: In case of error, display the navigation bar so that the user can leave this screen.
 * MXKAuthenticationViewController - Registration: support next_link from email validation.

Bug fixes:
 * The hint text animated weirdly horizontally after i send msgs.
 * MXKRoomDataSource: Fix infinite loop on initial pagination.
 * MXKAuthenticationViewController: The filled userId and password must be associated to the authentication session before launching email validation with next_link field.
 * MXKAuthenticationViewController: Fix registration cancellation.
 * Chat screen: lag during the history scrolling.
 * Chat screen: jump on an incoming messages when the user scrolls (even with no back pagination).
 * Chat screen: wrong attachment is opened.
 * Wrong application icon badge number.

Changes in MatrixKit in 0.3.5 (2016-04-08)
===============================================

Improvements:
 * MXKAccountManager: API change - [openSessionForActiveAccounts] is replaced by [prepareSessionForActiveAccounts]. This new method checks for each enabled account if a matrix session is already opened. It opens a matrix session for each enabled account which doesn't have a session.
 * MXK3PID: support new email binding mechanism.
 * MXKAuthenticationViewController, MXKAuthInputsView: Support registration based on MXAuthenticationSession class.
 * MXKAuthenticationRecaptchaWebView: Display a reCAPTCHA widget into a webview.
 * MXKAccountDetailsViewController: Handle the linked emails.
 * MXKAccount: Store (permanently) 3PIDs.
 * MXKRecentsDataSource: Remove room notifications and room tags handling (These operations are handled by inherited classes).
 * MXKContactManager: List email addresses from the local address book (see 'localEmailContacts').
 * MXKAccountManager: Added accountKnowingRoomWithRoomIdOrAlias method.

Bug fixes:
 * Search: 'no result' label is persistent #75.
 * MXKAccount: the push gateway URL must be configurable #76.
 * Multiple invitations on Start Chat action.

Changes in MatrixKit in 0.3.4 (2016-03-17)
===============================================

Improvements:
 * MXKWebViewViewController: add view controller for webview display.

Bug fixes:
 * Chat Screen: scrolling to bottom when opening new rooms seems unreliable.
 * Chat Screen: Wrong displayName and wrong avatar are displayed on invitation.
 * Chat Screen: Some messages are displayed twice.
 * Chat Screen: Some unsent messages are persistent.
 * Fix missing loading wheel when app is resumed.

Changes in MatrixKit in 0.3.3 (2016-03-07)
===============================================

Improvements:
 * Upgrade MatrixSDK version (v0.6.3).
 * MXKRoomDataSourceManager: Handle the current number of unread messages that match the push notification rules.
 * MXKRoomDataSource: Remove the timestamp of unsent messages on data reload.
 * MXKRoomViewController: Support the display of a timeline from the past.
 * MXKRoomBubbleCellData: Improve the computation of the text components position.
 * MXKViewControllerHandling: Define the default tint of the navigation bar.
 * MXKViewControllerHandling: Add flag to disable navigation bar tint color change on network status change.
 * MXKRoomBubbleTableViewCell: Add property to disable the default handling of the long press on event.
 * MXKRoomMemberDetailsViewController has been refactored.
 * MXKRoomInputToolbarView: Tells the delegate that the user is typing when textView did begin editing.
 * MXKRoomInputToolbarView: Add option to enable media auto saving.
 * MXKRoomViewController: Add missing constraint on Activities view.

Bug fixes:
 * MXKEventFormater: Fixed crash ("NSConcreteMutableAttributedString add Attribute:value:range:: nil value") when trying to display bad formatted links.
 * MXKRoomDataSource: At startup, recents are not updated for rooms with a gap during server sync.
 * MXKAttachmentsViewController: Remove play icon on videos while they're playing.
 * MXKRoomDataSource: A sent message may appear as unsent.
 * MXKRoomViewController: Fixed jumps when going forwards. Backwards pagination should be smoother.

Changes in MatrixKit in 0.3.2 (2016-02-09)
===============================================

Improvements:
 * Upgrade MatrixSDK version (v0.6.2).
 * MXKRoomViewController: Avoid to make pagination request when opening the page while there may be messages available in the store.
 * MXKViewController/MXKTableViewController: Activity indicator. Do not show it if the stopActivityIndicator is called just after (less than 0.3s)
 * Handle email invitation.

Bug fixes:
 * Messages being sent (echoes) were sometimes displayed in red.
 * Deleted unsent messages keep coming back when the app is relaunched.
 * If messages arrive whilst you are scrolled back, the scroll offset jumps.

Changes in MatrixKit in 0.3.1 (2016-01-29)
===============================================

Improvements:
 * Upgrade MatrixSDK version (v0.6.1).
 * MXKAuthenticationViewController: Keep the current inputs view when it is still relevant after auth flow refresh.
 * MXKAuthenticationViewController: Improve scroller content size handling.

Changes in MatrixKit in 0.3.0 (2016-01-22)
===============================================

Improvements:
 * MXKDataSource: The table/collection view cell classes are now defined by the data source delegate (see README).
 * MXKRecentsDataSource: Add methods to get, leave or tag a room.
 * MXKRecentsDataSource: Add method to mute/unmute room notifications.
 * MXKRecentsDataSource: Add kMXSessionInvitedRoomsDidChangeNotification observer.
 * MXKSearchViewController: Add reusable view controller for messages search (add dedicated resources: MXKSearchDataSource, MXKSearchCellData, MXKSearchTableViewCell).
 * MXKEventFormatter: Add timeStringFromDate method to generate the time string of a date by considered the current system time formatting.
 * MXKRoomBubbleCellData: Add nullable ’senderAvatarPlaceholder’ property. It is used when url is nil, or during avatar download.
 * MXKAccount: Add the ‘replacePassword’ method.
 * MXKAccount: Enable Background Sync (Active when push body will contain ‘content-available’ key).
 * MXKRoomDataSource: Add a new flag 'useCustomReceipts' to disable the default display of read receipts by MatrixKit.
 * MXKRoomBubbleTableViewCell: Rename inherited classes (MXKRoomIncomingAttachmentWithoutSenderInfoBubbleCell…).
 * MXKRoomBubbleTableViewCell: Add overlay container.
 * MXKRoomBubbleTableView: Add member display name in text input when user taps on avatar.
 * MXKRoomBubbleTableViewCell: Add listener to content view tap.
 * MXKRoomBubbleTableViewCell: Add listener to long press on the avatar view.
 * MXKRoomBubbleTableViewCell: Improve cell height computation by introducing some constraints.
 * Replace MXKReceiptAvartarsContainer with MXKReceiptSendersContainer.
 * MXKReceiptSendersContainer: Handle read receipts for incoming messages too.
 * MXKAccount: Use “<Bundle DisplayName> (iOS)” as app display name for notification pusher.
 * MXKEventFormatter: Define properties to allow formatted string customization (color and font).
 * MXKContactManager: Define the modes of the contact creation from the room members.
 * MXKRoomSettingsViewController: Reusable view controller dedicated to room settings.
 * MXKRoomInputToolbarViewWithHPGrowingText: Define growingTextView as protected field.
 * NSBundle+MatrixKit: Customize the table used to retrieve the localized version of a string. If the key is not defined in this table, the localized string is retrieved from the default table "MatrixKit.strings".
 * MXKRoomViewController: Define as protected UIDocumentInteractionController items.
 * MXKRoomViewController: Implement infinite back pagination.
 * MXKRoomViewController: Move as protected the saved placeholder of text input.
 * MXKAttachmentViewController: Hide status bar.
 * MXKImageView: Make public the imageView used as subview (in readonly mode).
 * MXKMediaManager: Return asset URL in case of saving in user's library
 * MXKRoomCreationInputs: Replace image url with image.
 * Add MXKCollectionViewCell class to define custom UICollectionViewCell.
 * Add MXKTableViewCellWithLabelAndMXKImageView class.
 * MXKTools: Rename resizeImage to reduceImage.
 * MXKImageView: Remove ‘mediaInfo’ property.
 * MXKTools: Add method to convert an image to a pattern color.

Bug fixes:
 * SYIOS-183: Store in-progress messages. Pending and unsent messages are now stored.
 * SYIOS-180: Bad scrolling performance on iOS 9.
 * The pusher is deleted and recreated every time the app starts, which is a Bad Idea.
 * iOS breaks catastrophically if you try to attach a photo when landscape. 
 * SYIOS-196 - Performance issue in MXKContactManager when resuming the app.
 * App freezes during back pagination in #matrix-spam.
 * Bing messages are not highlighted in Recents on new login.

Changes in MatrixKit in 0.2.8 (2015-11-30)
===============================================

Improvements:
 * MXKRoomViewController: Add MXKRoomActivitiesView class to display typing information above the input tool bar.
 * MXKViewControllerHandling: remove automatically closed sessions.
 * MXKQueuedEvent: Removed the deep copy of the passed MXEvent.
 * MXKAccount: Use pusher app ids defined in defaults.plist.
 * MXKRoomBubble: Handle sender's name at MXKRoomBubbleTableViewCell level.

Bug fixes:
 * MXKAttachmentsViewController: Back failed on attachment view (iOS8).

Changes in MatrixKit in 0.2.7 (2015-11-13)
===============================================

Improvements:
 * MXKRoomBubbleTableViewCell: Improve resources handling.
 * MXKRoomMemberDetails: Display rounded picture.

Bug fixes:
 * App crashes on an invite event during events stream resume.
 * MXKRoomMemberTableViewCell: App crashes on room members list update.

Changes in MatrixKit in 0.2.6 (2015-11-12)
===============================================

Improvements:
 * MXKRoomDataSource: Reduce computation time on read receipts handling.
 * MXKRoomDataSource: Use only one dispatch queue to limit thread switchings.

Bug fixes:
 * MXKRoomDataSource: Fix performance regression (UI was refreshed even in case of no change).
 * MXKRoomDataSource: Fix "Missing messages in back pagination".

Changes in MatrixKit in 0.2.5 (2015-11-06)
===============================================

Improvements:
 * MXKAuthInputsView: Disable auto correction in login text fields.
 * MXKAccount: Support unrecognized certificate during authentication challenge from a server.
 * MXKRoomViewController: Display read receipts.
 * MXKRoomViewController: Remove blank page while opening a room view controller.
 * MXKRoomViewController: Improve scrolling by reducing lags effect.
 * MXKRoomViewController: Add a spinner in the table header in case of back pagination.
 * MXKRoomViewController: Improve chat history display: When a refresh is triggered whereas the user reads through the history, we anchor the event displayed at the bottom of the history. This is useful in case of screen rotation, event redactions and back pagination triggered by a third part.
 * MXKRoomDataSource: Disable merging mechanism on successive messages from the same sender. Only one event is displayed by bubble. This change was done to reduce scrolling lags.
 * MXKRoomDataSource: Room invitations are displayed as unread messages.
 * MXKAttachment: Add MXKAttachment class to handle room attachments
 * MXKAttachmentsViewController: Add MXKAttachmentsViewController class to display room attachments in a viewer.
 * MXKAppSettings: Define HTTP and HTTPS schemes.
 * MXKRecentListViewController: Display multiple accounts in a consistent order.
 * MXKAuthenticationViewController: Support login fallback option.
 * Optimization: Thumbnail images are stored in a memory cache (LRU cache) to reduce file system access.
 * MXKRoomDataSourceManager: Memory warnings are now handled by MXKRoomDataSourceManager instances to reload unused data source. Matrix session reload is not triggered anymore (fix blank recents on memory warnings).

Bug fixes:
 * SYIOS-126: Timezone changes are not reflected into the app.
 * SYIOS-143: When you send a panorama, it doesn't tell you the resolutions it's targetting, and the predicted res and sizing are tiny. keyboard.
 * SYIOS-152: Time stamps don't obey the system formatting.
 * SYIOS-163: Add ability to see if an image has been sent or not.
 * SYIOS-170: Public Room: room history is wrong when user joins for the second time.
 * SYIOS-171 Cannot create public room in iOS console.
 * MXKRoomBubbleCellData: App crashes during bubble components update.
 * MXKRoomViewController: White stripe on animated gif.
 * MXKTableViewController: Infinite loop on view controller presentation.
 * MXKViewController: In Recents, keyboard gap remains despite there being no.
 * MXKRoomBubbleTableViewCell: Attached images without width and height appear as tiny in chat history.
 * MXKRoomBubbleTableViewCell: The app failed to show in full screen attached image without width and height.
 * MXKImageView: Infinite loading wheel in case of failure during downloading.
 * MXKRecentCellData: Should fix App freeze on last message refresh.
 * MXKContact: Bug Fix App crashed on a fake contact.

Changes in MatrixKit in 0.2.4 (2015-10-14)
===============================================

Improvements:
 * MXKAuthenticationViewController: Strip whitespace around usernames.

Bug fixes:
 * MXKAuthenticationViewController: App crashes in authentication screen on iOS 9.

Changes in MatrixKit in 0.2.3 (2015-09-14)
===============================================

Improvements:
 * MXKRoomViewController: Support animated gif.
 * MXKRoomInputToolbarView: Add ability to paste items from pasteboard (image, video and doc).
 * MXKContact: Consider matrix ids during search session.
 * MXKContactTableCell: Add custom accessory view.
 * MXKContactTableCell: Add options to customize thumbnail display box.
 * MXKRoomDataSourceManager: Register the MXKRoomDataSource-inherited class which is used to instantiate all room data source objects.
 * MXKRoomDataSource: Add pagination per day for rendered bubble cells.
 * MXKDataSource: Add a new step to finalize the initialisation after a potential customization.
 * MXKRoomBubbleCellData: Rename "isSameSenderAsPreviousBubble" flag with "shouldHideSenderInformation".
 * MXKRoomViewController: Animate toolbar height change.
 * Add predefined UITableViewCell classes: MXKTableViewCellWithSearchBar and MXKTableViewCellWithLabelAndImageView.
 
Bug fixes:
 * MXKRoomCreationView: Only private option is displayed.
 * MXKRecentListViewController: The room title overlaps the last message timestamp.
 * Attachments: pptx and similar files are not actually viewable.
 * Attachments: Recorded videos are not saved in user's photo library.

Changes in MatrixKit in 0.2.2 (2015-08-13)
===============================================

Improvements:
 * MXKRecentsDataSource: handle recents edition at MatrixKit level.
 * Add MXKRoomCreationInputs to list fields used during room creation.
 
Bug fixes:
 * Bug fix: App crashes on resume via a push notification.

Changes in MatrixKit in 0.2.1 (2015-08-10)
===============================================

Improvements:
 * MXKAccountDetailsViewController: Add UI to support global notification settings.
 * MatrixKit Error handling: Post MXKErrorNotification event on error.
 * MXKRoomDataSource: Reduce memory usage.
 * MXKRoomDataSource: In case of redacted events, merge adjacent bubbles if they are related to the same sender.
 * Localization: Add localized strings in MatrixKitAssets bundle.
 
Bug fixes:
 * Bug Fix: MXKRoomViewController - App crashes when user selects copy in text input view.
 * Bug Fix: App crashes when user press "Logout all accounts".

Changes in MatrixKit in 0.2.0 (2015-07-10)
===============================================

Improvements:
 * MXKAuthenticationViewController: add reusable UI for authentication.
 * MXKAccount: add MXKAccount object which contains the credentials of a
   logged matrix user. It is used to handle matrix session and presence for
   this user.
 * MXKAccount: Handle Remote and In-App notifications at account level.
 * MXKAccount: clear session store on account logout.
 * MXKAccountManager: support multi-sessions. Existing account may be disabled
   without logout.
 * MXK3PID: Move MXC3PID class in MatrixKit.
 * MXKAccountDetailsViewController: Edit matrix account profile.
 * MXKAccountTableViewCell: reusable model of table view cell to display
   Matrix account.
 * MXKRecentListViewController: search in recents is optional feature.
 * MXKRecentListViewController: In case of multi-sessions recents may be
   interleaved or not. Each session may be collapsed or not.
 * MXKRecentListViewController: Lock recents refresh during server sync 
   (prevent recents flickering during server sync).
 * MXKAppSettings: Define user's presence colour.
 * MXKEventFormatter: Expose colours used when formatting events into
   attributed strings.
 * MXKRoomViewController: Handle progress text input saving (optional
   feature).
 * MXKRoomViewController: Prompt user to select a compression level before
   sending image.
 * MXKRoomViewController: support attachment saving and sharing.
 * MXKRoomViewController: Highlight selected text in bubble.
 * MXKRoomViewController: Support attached files (download/open/share).
 * MXKRoomViewController: Post unrecognised IRC-style command as a message.
 * MXKRoomDataSource: cache sent media (we don't need to download outgoing
   media).
 * MXKRoomBubbleTableViewCell: Make it more reusable. Removed all #define
   constants that take values from xibs.
 * MatrixKit Sample: Update Sample app.
 * Add reusable models of table view cells (MXKTableViewCellWithButton,
   MXKTableViewCellWithLabelAndSwitch...)
 * MXKCallViewController: Add reusable view controller to handle voice and
   video call.
 * MXKRoomTitleView: Add reusable view to handle room title display and
   edition.
 * MXKRoomTitleViewWithTopic: inherit MXKRoomTitleView to handle room topic.
 * MXKRoomCreationView: Add reusable view to handle room creation.
 * MXKPublicRoomTableViewCell: Add reusable table view cell to display public
   room.
 * MXKViewController and MXKTableViewController: support multi-sessions for
   all inherited class.
 * MXKContactManager: Move contacts handling in MatrixKit.
 * MXKContactListViewController: Add reusable view controller to list
   contacts.
 * MXKRecents: add "Mark all as read" option.
 * MXKAccount: add the account user's tint colour: a unique colour fixed by
   the user id. This tint colour may be used to highlight rooms which belong
   to this account's user.
 * Move Images and Sounds into MatrixKitAssets bundle.
 * Add MXKContactDetailsViewController and MXKRoomMemberDetailsViewController.
 
Bug fixes:
 * Bug Fix in registration: the home server base URL was wrong after the
   creation of a new account, which made all requests fail.
 * MXKImageView: Fix button display issue in fullscreen in app without tab
   bar.
 * MXKRoomViewController: Display loading wheel on initial back pagination.
 * MXKRoomViewController: Fix UI refresh when user leaves the current selected
   room.
 * MXKRoomDataSource Manager: add method to release unused manager.
 * Bug Fix: App crash: missing error domain in case of MXKAuthentication
   failure
 * Memory leaks: Dispose properly view controller resources.
 * Performance issue in MXKRoomMembersListViewController: Update correctly
   member's activity information.
 * MXKAppSettings: Add missing synchronise.
 * MXKRoomViewController: Fix scrolling issue when keyboard is opened.
 * MXKRoomViewController: Prevent scroll bounce on keyboard dismiss.
 * MXKRoomViewController: dismiss keyboard when a MXKAlert is presented.
 * Bug Fix: MXKRoomBubbleCellData - "Unsent" button is displayed at the wrong
   place, and it is not active.
 * Bug Fix: Restore download/upload cancellation.
 * Performance issue: Fix issue related to table view cell dequeuing.
 * Bug Fix: MXKImageView - The high resolution image is not displayed on full
   screen at the end of download.
 * Bug Fix: Toggle default keyboard from 123 mode to ABC mode when send button
   is pressed.
 * Bug Fix iOS7: MXKRoomViewController - bubble width is wrong for messages
   ended with 'w' or 'm' character.
 * Bug Fix: When the app is backgrounded during a server sync, the pause is
   postponed at the end of sync.
 * Bug Fix: the client spam the server with setPresence requests.
 * Bug Fix: Blank room - Handle correctly failure during back pagination
   request (see SYN-162 - Bogus pagination token when the beginning of the
   room history is reached).


Changes in MatrixKit in 0.1.0 (2015-04-23)
===============================================

First release.
MatrixKit contains the following reusable UI components:

 * MXKRoomViewController
 * MXKRecentListViewController
 * MXKRoomMemberListViewController
 

