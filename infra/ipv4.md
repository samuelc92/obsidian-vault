# IPv4 Address Structure

- An IPv4 address is written using dotted decimal notation, but it is actually a 32-bit address. The 32-bit are divided into four 8-bits sections called octets. Then, the octets are converted into a decimal value.
- The range of an IPv4 can be from 0.0.0.0 to 255.255.255.255
- An IPv4 address has two main parts
	- An network portion
	- A host portion

## Subnet Mask

- The subnet mask separates the network portion from the host portion of the IPv4 address.
- A subnet mask is 32 bits long. It has a group of 1s following by a group of 0s. The 1s indicate the network and the 0s indicate the host. 

### Finding the IPv4 Network Address Using The Subnet Mask

- Example: IPv4 (192.168.1.100) and subnet mask (255.255.255.0)
- It is performed a bitwise AND operation between the host address and the subnet mask in binary notation. For each bit position, if both the address and mask bits are 1, the result is 1. Otherwise, the result is 0.
- Result: Network portion (192.168.1) and the host portion (0) or /8.
