# propertytransfer
// SPDX-License-Identifier: MIT
<br>
 pragma solidity ^ 0.8.0;
 <br>
contract Propertytransfer{<br>
    struct Property{<br>
    string name;<br>
    address owner;<br>
    uint value;<br>
    uint area;<br>
    }<br>
    mapping (uint=>Property) public properties;<br>
    function addProperty(
        uint _id,
        string memory name,
        uint _value,
        uint _area) public { <br>
            properties[_id].name= name;<br>
            properties[_id].owner= msg.sender;<br>
            properties[_id].value=_value;<br>
            properties[_id].area=_area;<br>
        }<br>
        function queryPropertyById (uint _id) public view <br>
        returns (string memory name , address owner, uint value, uint area) <br>
        { <br>
            return (
                properties[_id].name,properties[_id].owner,properties[_id].area,properties[_id].value); <br>
                }<br>
                 function transfer (uint8 _id, address _newOwner) public { <br>
                    properties[_id].owner=_newOwner; <br>
                } <br>
         }
