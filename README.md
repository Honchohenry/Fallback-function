# Fallback-function
// SPDX-License-Identifier: GPL-3.0

pragma solidity >=0.7.0 <0.9.0;
contract  SampleFallback {

    uint public lastValueSent;
    string public LastFunctionCall;

    receive() external payable {
        lastValueSent = msg.value;
        LastFunctionCall = "receive";

    }

    fallback() external payable { 
        lastValueSent = msg.value;
        LastFunctionCall = "fallback";
    }

}

#     Another Fallback

// SPDX-License-Identifier: GPL-3.0

pragma solidity >=0.7.0 <0.9.0; 

contract Fallback {

    event Received(address sender, uint amount, string message);

    receive() external payable { 
        emit Received(msg.sender, msg.value, "fallback was called");
    }

    fallback() external payable {
        emit Received(msg.sender, msg.value, "Fallback was called");

    }

    function getBalance() public view returns (uint) {
        return address(this).balance;
    }

   

}
