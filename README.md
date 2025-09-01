# Rrepository-alx-airbnb-database
database-adv-script
/* ==========================================================
   INNER JOIN
   Retrieve all bookings and the respective users who made them
   ========================================================== */
SELECT 
    b.id AS booking_id,
    b.property_id,
    b.start_date,
    b.end_date,
    u.id AS user_id,
    u.name AS user_name,
    u.email AS user_email
FROM bookings b
INNER JOIN users u
    ON b.user_id = u.id;


/* ==========================================================
   LEFT JOIN
   Retrieve all properties and their reviews,
   including properties that have no reviews
   ========================================================== */
SELECT 
    p.id AS property_id,
    p.name AS property_name,
    p.location,
    r.id AS review_id,
    r.rating,
    r.comment
FROM properties p
LEFT JOIN reviews r
    ON p.id = r.property_id;


/* ==========================================================
   FULL OUTER JOIN
   Retrieve all users and all bookings,
   even if the user has no booking or a booking is not linked to a user
   ========================================================== */
SELECT 
    u.id AS user_id,
    u.name AS user_name,
    u.email AS user_email,
    b.id AS booking_id,
    b.property_id,
    b.start_date,
    b.end_date
FROM users u
FULL OUTER JOIN bookings b
    ON u.id = b.user_id;
