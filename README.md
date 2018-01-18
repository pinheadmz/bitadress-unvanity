For Cryptograffiti: https://twitter.com/cryptograffiti/status/954099904447524864

1. go to https://www.bitaddress.org and give it entropy
2. opt+cmd+J to open javascript console
3. paste the code below
4. at prompt, enter the characters you hate!

The more you hate, the longer it takes to generate 


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
