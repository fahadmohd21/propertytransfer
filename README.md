# propertytransfer
// SPDX-License-Identifier: MIT
 pragma solidity ^ 0.8.0;
contract Propertytransfer{
    struct Property{
    string name;
    address owner;
    uint value;
    uint area;
    }
    mapping (uint=>Property) public properties;
    function addProperty(
        uint _id,
        string memory name,
        uint _value,
        uint _area) public { 
            properties[_id].name= name;
            properties[_id].owner= msg.sender;
            properties[_id].value=_value;
            properties[_id].area=_area;
        }
        function queryPropertyById (uint _id) public view 
        returns (string memory name , address owner, uint value, uint area)
        {
            return (
                properties[_id].name,properties[_id].owner,properties[_id].area,properties[_id].value);
                }
         }
