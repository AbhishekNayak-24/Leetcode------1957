# Leetcode------1957
Delete Characters to Make Fancy String
//Code in java 
class Solution {
    public String makeFancyString(String s) {
        StringBuilder sb = new StringBuilder(); // Use StringBuilder for efficient string manipulation

        for (char c : s.toCharArray()) { // Iterate through each character in the input string
            // Check if adding the current character 'c' would result in three consecutive identical characters
            // This condition is true if:
            // 1. The StringBuilder has at least two characters already (sb.length() >= 2)
            // 2. The last character in StringBuilder is 'c' (sb.charAt(sb.length() - 1) == c)
            // 3. The second to last character in StringBuilder is also 'c' (sb.charAt(sb.length() - 2) == c)
            if (sb.length() >= 2 && sb.charAt(sb.length() - 1) == c && sb.charAt(sb.length() - 2) == c) {
                continue; // If adding 'c' would create a triple, skip it
            } else {
                sb.append(c); // Otherwise, append the character to the StringBuilder
            }
        }
        return sb.toString(); // Convert the StringBuilder to a String and return
    }
}
