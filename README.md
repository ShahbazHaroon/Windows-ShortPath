# Windows-ShortPath
How to Create Short Path for Windows Folders or Directories

<p>By default Windows has a feature to create short path for folders</p>

<p>To list short path for folders in Windows, you need to run the command dir /x</p>

<figure>
    <img src="https://github.com/ShahbazHaroon/Windows-ShortPath/blob/master/img/how-to-list-short-paths-in-windows.png" alt="erlang installer choose components" />
</figure>

<p>For example, in the above picture, you can see that INTERN~1 is a short path for Internet Explorer. So, instead of using C:\Program Files\Internet Explorer, you can use C:\PROGRA~1\INTERN~1 (doing dir /x at the C drive location, I found that PROGRA~1 is short path for Program Files).</p>

<p>However, you can also see in the picture that the folder “Puppet Labs” does not have a short path yet and I need to use this path for some advanced level work with PeopleSoft DPKs. So, I need to create a short path for Puppet Labs.</p>

<h2>How to Create Short Path for Windows Folders or Directories</h2>

<p>This feature of creating short names in Windows is known as <strong>8dot3 name</strong></p>

<p>Step 1 — Verify if the feature to create short path is enabled or not. Run the command by invoking command prompt in administrative mode: <strong><em>fsutil 8dot3name query</em></strong></p>

<p>If you get response like “Registry state is 1” then its disabled.<br>
If you get response like “Registry state is 0” then its enabled. If it is disabled, then you need to enable it before you can create a short path.</p>

<p>Step 2 — If disabled, enable the short name feature using the command:</p>

<p><strong><em>fsutil behavior set disable8dot3 0</em></strong></p>

<p>Step 3 — To create new short path for a folder, you need to use a command with generic syntax:</p>

<p><strong><em>fsutil file setshortname &lt;Path&gt; &lt;Shortname&gt;</em></strong></p>

<p>Example : <strong><em>fsutil file setshortname “C:\Program Files\Puppet Labs” PUPPET~1</em></strong></p>

<p>Now do a listing using dir /x&nbsp; and you should be able to see the short name of your folder.</p>

<figure>
    <img src="https://github.com/ShahbazHaroon/Windows-ShortPath/blob/master/img/create-windows-short-name-for-folders.png" alt="erlang installer choose components" />
</figure>

<p>You are now set to use this short path. If you wish to, disable this feature again using the command”

<p><em><strong>fsutil behavior set disable8dot3 1</strong></em></p>
