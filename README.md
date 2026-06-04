// SPDX-License-Identifier: GPL-3.0

pragma solidity >=0.7.0 <0.9.0; contract SampleFallback {

        uint public lastValueSent;
        uint public totalReceived;
        string public lastfunctionCalled;

        receive() external payable{
           lastValueSent = msg.value;
           totalReceived += msg.value; 
           lastfunctionCalled = "receive";
        }

        fallback() external payable {
            lastValueSent = msg.value;
            totalReceived += msg.value;
            lastfunctionCalled =  "fallback";
         }
}
