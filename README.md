# Mock_SQL

Please submit the interview problems posted in slack channel here. The problems and statements are intentionally not shown here so that students are not able to see them in advance 


-----------------------------------------------------------------------
Write a solution to report the distance traveled by each user.

Return the result table ordered by travelled_distance in descending order, if two or more users traveled the same distance, order them by their name in ascending order.

The result format is in the following example.
-------------------------------------------------------

 

Example 1:

 
SELECT 
    u.name AS name,
    COALESCE(SUM(r.distance), 0) AS travelled_distance
FROM 
    Users u
LEFT JOIN 
    Rides r ON u.id = r.user_id
GROUP BY 
    u.id, u.name
ORDER BY 
    travelled_distance DESC, u.name;
