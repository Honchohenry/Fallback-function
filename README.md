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
