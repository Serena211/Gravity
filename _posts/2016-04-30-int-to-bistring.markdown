---
layout: post
title:  "Int to BiString"
date:   2016-04-30 19:45:31 +0530
categories: algorithms
author: "Serena Liu"
---
<pre>
	/**
	 * Converts an integer to a 32-bit binary string
	 * @param number
	 *      The number to convert
	 * @param groupSize
	 *      The number of bits in a group
	 * @return
	 *      The 32-bit long bit string
	 */
	public String intToString(int number, int groupSize) {
	    StringBuilder result = new StringBuilder();

	    for(int i = 31; i >= 0 ; i--) {
	        int mask = 1 << i;
	        result.append((number & mask) != 0 ? "1" : "0");

	        if (i % groupSize == 0)
	            result.append(" ");
	    }
	    result.replace(result.length() - 1, result.length(), "");

	    return result.toString();
	}

</pre>
