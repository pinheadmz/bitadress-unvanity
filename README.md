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
