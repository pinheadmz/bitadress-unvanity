For Cryptograffiti: https://twitter.com/cryptograffiti/status/954099904447524864

1. go to https://www.bitaddress.org and give it entropy (move mouse around until it says 100% and shows you a QR code)
2. opt+cmd+J to open javascript console
3. paste the code below into the console and hit enter
4. at the prompt, enter the characters you hate! (ex: sS) and hit enter again

The console will generate addresses until it finds one that doesn't have those characters in it:
(The more you hate, the longer it takes to generate!)

Example output:
~~~~
0 "s" 0
1 "S" 22
0 "s" 23
0 "s" 5
0 "s" 17
1 "S" 32
0 "s" 8
1 "S" 18
0 "s" 9
5JJcKxTuKu6UoXc1Mm9KuWe3ogEi6bhriDJbtiqNTZB9T6s2ge5 1PqrPue7p9iX9qYF8n9PboVMjBgER5tXt7
~~~~
That's your PRIVATE key and Bitcoin address!

Here's the code to paste!
~~~~
var xStr = prompt();
var xList = xStr.split('');
var addr = xStr;
var key = 0;
function testAddr(xList, addr){
	for (var c=0; c<xList.length; c++){
		if (addr.indexOf(xList[c])!= -1){
			console.log(c, xList[c], addr.indexOf(xList[c]));
			return false;
		}
	}
	return true;
}

while (!testAddr(xList, addr)){
	key = new Bitcoin.ECKey(false);
	addr = key.getBitcoinAddress();
}

console.log(key.getBitcoinWalletImportFormat(), addr);
~~~~
