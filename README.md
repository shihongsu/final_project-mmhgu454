# Life_Game  
 生命遊戲介紹：https://zh.wikipedia.org/wiki/%E5%BA%B7%E5%A8%81%E7%94%9F%E5%91%BD%E6%B8%B8%E6%88%8F

## 程式使用方法
* 下載Life_Game.m程式放在MATLAB資料夾中，
* 在command window中輸入Life_Game以執行程式。
* 要求使用者在command window中選擇生命遊戲的範圍大小，
* 問使用者想要自己選取點點還是由程式自動生成，  

若選擇自己選取，則會跳出figure視窗讓使用者選取要點的地方，  
若選擇由程式生成，會再請使用者輸入要生成多少黑點。  
  
以上輸入完成後，程式會先暫停兩秒鐘，讓使用者看清楚第零代時，細胞的分布狀況，  
接下來會以最快每0.05秒一次的速度逐一演示細胞擴散、衰退的過程，  
若最後細胞維持靜態平衡，程式會在command window提示並結束，  
否則會在演示兩千次(大約兩分鐘)後強制停下(可能還沒演示完。也有可能是各種動態平衡)。  

## 程式架構：
主要由一個三維矩陣（由於要使用image函數，需要有NxNx3的陣列）--A  
及一個相同大小的二維陣列(NxN)構成，　　　　　　　　　　　　　--B  
A用來表示當前的各個位置細胞死活狀態，
B用來表示下一代的細胞分布會如何改變，  
image(A)-->計算A有哪些會改變-->存在B裡面-->根據B改變A-->歸零B-->image(A)-->loop
