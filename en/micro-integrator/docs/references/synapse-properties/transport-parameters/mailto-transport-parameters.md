# MailTo Transport

## About the MailTO transport

When you use the Micro Integrator to mediate messages, the mediation sequence can be configured to send emails (over SMTP) or receive emails (Over POP3 or IMAP) by using the MailTo transport protocol.

The MailTo transport listener implementation can be configured by setting the parameters as described in the JavaMail API documentation. For IMAP related properties, see [IMAP Package Summary](https://javaee.github.io/javamail/docs/api/com/sun/mail/imap/package-summary.html). For POP3 properties, see [POP3 Package Summary](https://javaee.github.io/javamail/docs/api/com/sun/mail/pop3/package-summary.html). The MailTo transport listener also supports the following transport parameters in addition to the parameters described in the JavaMail API documentation.

## Parameters

Given below is the list of MailTo transport parameters that can be configured when you [create a proxy service](../../../develop/creating-artifacts/creating-a-proxy-service.md).

<table>
   <thead>
      <tr class="header">
         <th>
            <p>Parameter Name</p>
         </th>
         <th>
            <p>Description</p>
         </th>
         <th>
            <p>e.g.Required</p>
         </th>
         <th>
            <p>Possible Values</p>
         </th>
         <th>
            <p>Default Value</p>
         </th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>
            <p><code>              transport.mail.Address             </code></p>
         </td>
         <td>
            <p>The mail address from which this service should fetch incoming mails.</p>
         </td>
         <td>
            <p>Yes</p>
         </td>
         <td>
            <p>A valid e-mail address</p>
         </td>
         <td><br /></td>
      </tr>
      <tr class="even">
         <td><code>             transport.mail.bodyWhenAttached            </code></td>
         <td>
            <p>The content for the body of the mail when sending a mail with an attachment.</p>
         </td>
         <td>No</td>
         <td>The text you want to appear in the mail body</td>
         <td><br /></td>
      </tr>
      <tr class="odd">
         <td>
            <p><code>              transport.mail.Folder             </code></p>
         </td>
         <td>
            <p>The mail folder in the server from which the listener should fetch incoming mails.</p>
         </td>
         <td>
            <p>No</p>
         </td>
         <td>
            <p>A valid mail folder name (e.g., inbox)</p>
         </td>
         <td>
            <p>inbox folder if that is available or else the root folder</p>
         </td>
      </tr>
      <tr class="even">
         <td>
            <p><code>              transport.mail.Protocol             </code></p>
         </td>
         <td>
            <p>The mail protocol to be used to receive messages.</p>
         </td>
         <td>
            <p>No</p>
         </td>
         <td>
            <p><em>pop3, imap</em></p>
         </td>
         <td>
            <p>imap</p>
         </td>
      </tr>
      <tr class="odd">
         <td>
            <p><code>              transport.mail.PreserveHeaders             </code></p>
         </td>
         <td>
            <p>A comma separated list of mail header names that this receiver should preserve in all incoming messages.</p>
         </td>
         <td>
            <p>No</p>
         </td>
         <td>
            <p>A comma separated list</p>
         </td>
         <td><br /></td>
      </tr>
      <tr class="even">
         <td>
            <p><code>              transport.mail.RemoveHeaders             </code></p>
         </td>
         <td>
            <p>A comma separated list of mail header names that this receiver should remove from incoming messages.</p>
         </td>
         <td>
            <p>No</p>
         </td>
         <td>
            <p>A comma separated list</p>
         </td>
         <td><br /></td>
      </tr>
      <tr class="odd">
         <td>
            <p><code>              transport.mail.ActionAfterProcess             </code></p>
         </td>
         <td>
            <p>Action to perform on the mails after processing them.</p>
         </td>
         <td>
            <p>No</p>
         </td>
         <td>
            <p><em>MOVE, DELETE</em></p>
         </td>
         <td>
            <p>DELETE</p>
         </td>
      </tr>
      <tr class="even">
         <td>
            <p><code>              transport.mail.ActionAfterFailure             </code></p>
         </td>
         <td>
            <p>Action to perform on the mails after a failure occurs while processing them.</p>
         </td>
         <td>
            <p>No</p>
         </td>
         <td>
            <p><em>MOVE, DELETE</em></p>
         </td>
         <td>
            <p>DELETE</p>
         </td>
      </tr>
      <tr class="odd">
         <td>
            <p><code>              transport.mail.MoveAfterProcess             </code></p>
         </td>
         <td>
            <p>Folder to move the mails after processing them.</p>
         </td>
         <td>
            <p>Required if ActionAfterProcess is MOVE</p>
         </td>
         <td>
            <p>A valid mail folder name</p>
         </td>
         <td><br /></td>
      </tr>
      <tr class="even">
         <td>
            <p><code>              transport.mail.MoveAfterFailure             </code></p>
         </td>
         <td>
            <p>Folder to move the mails after encountering a failure.</p>
         </td>
         <td>
            <p>Required if ActionAfterFailure is MOVE</p>
         </td>
         <td>
            <p>A valid mail folder name</p>
         </td>
         <td><br /></td>
      </tr>
      <tr class="odd">
         <td>
            <p><code>              transport.mail.ProcessInParallel             </code></p>
         </td>
         <td>
            <p>Whether the receiver should process incoming mails in parallel or not. This works only if the mail protocol supports processing incoming mails in parallel. (e.g., IMAP)</p>
         </td>
         <td>
            <p>No</p>
         </td>
         <td>
            <p><em>true, false</em></p>
         </td>
         <td>
            <p>false</p>
         </td>
      </tr>
      <tr class="even">
         <td>
            <p><code>              transport.ConcurrentPollingAllowed             </code></p>
         </td>
         <td>
            <p>Whether the receiver should poll for multiple messages concurrently.</p>
         </td>
         <td>
            <p>No</p>
         </td>
         <td>
            <p><em>true, false</em></p>
         </td>
         <td>
            <p>false</p>
         </td>
      </tr>
      <tr class="odd">
         <td>
            <p><code>              transport.mail.MaxRetryCount             </code></p>
         </td>
         <td>
            <p>Maximum number of retry operations to be performed when fetching incoming mails.</p>
         </td>
         <td>
            <p>Yes</p>
         </td>
         <td>
            <p>A positive integer</p>
         </td>
         <td><br /></td>
      </tr>
      <tr class="even">
         <td>
            <p><code>              transport.mail.ReconnectTimeout             </code></p>
         </td>
         <td>
            <p>The reconnect timeout in milliseconds to be used when fetching incoming mails.</p>
         </td>
         <td>
            <p>Yes</p>
         </td>
         <td>
            <p>A positive integer</p>
         </td>
         <td><br /></td>
      </tr>
   </tbody>
</table>