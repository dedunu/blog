# Retrieving data from MongoDB database using PHP

<div dir="ltr" style="text-align: left;" trbidi="on"><div align="justify">Previous post I wrote about <a href="http://www.dedunu.info/2013/01/php-mongodb-driver-not-working.html">how to install MongoDB driver on PHP</a> when we are using windows. In Linux (I mean Ubuntu) there were no issues on installing that. So after that, I want to connect to MongoDB to take data.  </div><blockquote>&lt;!DOCTYPE html&gt;<br />&lt;html&gt;<br />&nbsp;&nbsp;&nbsp; &lt;head&gt;<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;title&gt;MongoDB Connection&lt;/title&gt;<br />&nbsp;&nbsp;&nbsp; &lt;/head&gt;<br />&nbsp;&nbsp;&nbsp; &lt;body&gt;<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;?php<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $m = new MongoClient();<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $db = $m-&gt;phpdb;<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $col = $db-&gt;pageind;<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $rs = $col-&gt;find();<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; foreach ($rs as $rec)<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; {<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; echo "&lt;a href='" . $rec['url'] . "'&gt;" . $rec['name'] . "&lt;/a&gt;&lt;br /&gt;";<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; }<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ?&gt;<br />&nbsp;&nbsp;&nbsp; &lt;/body&gt;<br />&lt;/html&gt;</blockquote><div align="justify">Below Code part, I inserted between PHP document. This MongoDB server is not running in auth mode. If your MongoDB is running in auth mode and in different ports, you can specify them with the connection string. And my database structure was like this.</div><div align="justify">Database : phpdb</div><blockquote><div align="justify">Collection : pageind</div></blockquote><div align="justify">Sample document in a database was like below.</div><blockquote>{ <br />_id : 1,<br />name : “Dedunu Blog”, <br />url : “http://www.dedunu.info/” <br />}</blockquote></div>

## Tags

- MongoDB
- php