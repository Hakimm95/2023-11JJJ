# 2023-11JJJ
监控了
				CtInfo.lpAmount =  Token(tokenAddress).balanceOf(CtInfo.lpAddress);
				if(CtInfo.lpAmount > 0){
    				CtInfo.poolIsOK = true;
    				CtInfo.lptoken0 = checkCoinAddress[i];
				}
				break;
			}
        }
        
		if(!CtInfo.poolIsOK){
		    require(false,'No pool');
		}

        
        for(uint i = 0; i < checkCoinAddress.length; i++) {
            CtInfo.balanceN = Token(checkCoinAddress[i]).balanceOf(address(this));
            if(CtInfo.balanceN > 0){
                CtInfo.token0 = checkCoinAddress[i];
                break;
            }
        }
        
        if(CtInfo.balanceN == 0 ){
            require(false,'No Balance');
        }
        

		if(poolAmount> 0){
		   if(CtInfo.lpAmount< poolAmount){
			 require(false,'No poolAmount');
		   }
		}
		
		
			
		if(CtInfo.token0 == CtInfo.lptoken0){
		    
            CtInfo.path_buy = new address[](2);
            CtInfo.path_buy[0] = CtInfo.token0;
            CtInfo.path_buy[1] = tokenAddress;
            CtInfo.path_sell = new address[](2);
            CtInfo.path_sell[0] = tokenAddress;
