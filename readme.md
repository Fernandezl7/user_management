#                                                 IS601 Final Project: User Management System 
________________________________________
### Overview: 
The User Management System project [Project Link](https://github.com/Fernandezl7/user_management) has been a great development project, providing a comprehensive, real-world coding experience that closely mirrors professional software development environments. As someone with minimal experience in this area, I really appreciate the challenge yet doability of this project to help implement my skills learned from throughout the course. As part of this project, I concentrated on enhancing user profile management by integrating the Profile Picture Upload feature using Minio. Additionally, I worked on improving system functionality by implementing robust validation mechanisms, handling edge cases, and ensuring seamless user interactions.
This project allowed me to deepen my understanding of backend development, database management, and the integration of third-party tools. I also honed my debugging and problem-solving skills while collaborating in a structured environment.
By adhering to the best coding practices and leveraging tools like pytest for testing, I ensured the reliability and scalability of the features. This experience highlights my learning process, technical contributions, and personal growth throughout the project. It has significantly enhanced my ability to deliver efficient and user-centric solutions.
________________________________________
### Feature Implemented: Profile Picture Upload with Minio : [Feature Link](https://github.com/Fernandezl7/user_management/tree/addfeaturetouploadpfp)

This feature aims to improve user engagement by integrating profile picture upload functionality using Minio, a distributed object storage system. It provides users with the ability to personalize their accounts while ensuring secure and efficient management of profile pictures.This feature not only enhances user engagement by allowing profile personalization but also demonstrates the capability to integrate third-party systems like Minio effectively. By focusing on security, scalability, and user experience, it ensures a robust and user-centric implementation.
________________________________________
### Implementation Details:
1.	API Endpoint for Uploading Profile Pictures:
   
     -	Developed a POST /users/{id}/profile-picture API endpoint.
     -	Validate the uploaded files to ensure:
  	
            Supported formats: JPEG, PNG, GIF.
  	
  	        File size limits: e.g., up to 5MB.
  	
     -	Secure file names: Use unique identifiers (e.g., UUIDs) to prevent overwriting.
  	
2.	Secure Storage in Minio:
   
    -	Store profile pictures in a dedicated bucket. Applied bucket policies to enforce strict access controls.
  	
3.	Enhancements to User Profile API:
   
    -	Extend the User schema to include a profile_picture_url field.
    -	Update GET /users/{id} to return the profile picture URL alongside other user details.
  	
4.	Retrieve Profile Picture URL:
   
    -	Generate presigned URLs from Minio for secure and efficient retrieval.
    -	Ensure the URLs are dynamically included in user profile responses.
________________________________________
### Key Considerations in User Management Project

1.	Validation:
   
     Enforce strict validation for file types and sizes to prevent misuse and return clear error messages for invalid uploads.
  
2.	Security:

     Ensure all API communication occurs over HTTPS. Apply IAM policies to Minio buckets to restrict unauthorized access. Use presigned URLs with short expiration times for secure access.
  
3.	Scalability:
   
     Optimize bucket structure for large-scale storage. Implement caching for frequently accessed profile pictures.
  
4.	Error Handling:
   
    Return appropriate HTTP status codes:
  	
      -	400 Bad Request for invalid inputs.
    
      -	404 Not Found for missing user profiles or pictures.
   
      - 500 Internal Server Error for unexpected issues.
________________________________________
### Key Benefits

  •	Personalizes user profiles, enhancing the overall user experience.
  •	Ensures secure and scalable management of profile pictures using Minio.
  •	Improves the API functionality by integrating additional features like retrieval and dynamic URL generation.
________________________________________
### Testing and Validation ###

•	Unit Tests:

  Validated file uploads for supported and unsupported file types. Verified correct integration with Minio for storage and retrieval.
  
•	Integration Tests:

   Tested the complete workflow from upload to display. Ensure API endpoints return correct data for valid and invalid inputs.
________________________________________
This submission meets the following goals:
1.	Implements A NEW feature into the Existing User Management.
2.	Fixed 5+ QA Issues/Bugs across the codebase.
3.	Wrote 10+ NEW Tests for the NEW feature implemented.
4.	Includes a Reflection Document for the course.
5.	Includes Extensive Documentation of the feature, bugs and test cases implemented.
________________________________________
Issues Resolved:

Solved 5 major issues to improve the project:

1.	Fix the Docker File to allow build :  [Issue 1 link](https://github.com/Fernandezl7/user_management/issues/1)

      Updated the Docker File to allow build. Fixed the workflow action yml file to pass the build if the vulnerabilities are found. Fixed the Application throwing error due to library version mismatch.
 
2.	User ID is passed as None in the user verification email:  [Issue 2 link](https://github.com/Fernandezl7/user_management/issues/2)
   
        User ID is passed as None in the user verification email. Email will be sent only once when the user is added and updated in the database. Updated Code to fix user id showing as none in user verification email

3.	Enforce strong Password validation: [Issue 3 link](https://github.com/Fernandezl7/user_management/issues/3)
   
    •	Fixed the code to enforce strong password validation. This fix will ensure that the password meets several security criteria, such as length, inclusion of upper and lower case letters, digits, special characters, and avoiding spaces.
  	
    •	Length Check: Ensures the password is at least 8 characters long.
  	
    •	Uppercase Check: Ensures at least one uppercase letter ([A-Z]).
  	
    •	Lowercase Check: Ensures at least one lowercase letter ([a-z]).
  	
    •	Digit Check: Ensures at least one numeric digit (\d).
  	
    •	Special Character Check: Ensures at least one character from a set of common special characters.
  	
    •	No Spaces: Ensures the password does not contain spaces (\s)

4.	Fix the valid profile picture uploads: [Issue 4 link](https://github.com/Fernandezl7/user_management/issues/4)
   
    To ensure that the provided URL meets specific criteria, such as being well-formed and pointing to an image file.
  	
    Fixed the code to validate Proper URL format - Ends with valid image extensions (.jpg, .jpeg, .png, .gif)
  	
    To ensure secure and valid profile picture uploads, implemented robust URL validation by verifying that the input is a well-formed URL, ends with a standard image file extension such as .jpg, .png, or .gif, and optionally checking the URL's accessibility and content type to confirm it points to a valid image resource.

5.	Not able to update is professional user field [Issue 5 link](https://github.com/Fernandezl7/user_management/issues/5)
	
    The issue of not being able to update the is_professional field was resolved by identifying and addressing the missing field in the user schema.
    The is_professional field was added to both user_update and user_response schemas, ensuring proper data handling and seamless functionality for updates.
________________________________________
Testing and Quality Assurance :

•	Added 10+ test cases:  
[Minio tests](https://github.com/Fernandezl7/user_management/tree/UPDATETESTS)

By implementing these test cases, we can ensure a robust and user-friendly profile picture upload feature, while maintaining the security and reliability of the MinIO storage backend. 

________________________________________
Deployment:

•	Successfully deployed the project to DockerHub :	[DockerHub Repository](https://hub.docker.com/repository/docker/fernandezl0911/user/general)

•	Configured GitHub Actions for automated workflows :	[Successful Workflows](https://github.com/Fernandezl7/user_management/actions)

•	GitHub Repository: [User Management Project](https://github.com/Fernandezl7/user_management)
________________________________________

Course Reflection Document :  [IS601Final-Reflection-Doc](https://docs.google.com/document/d/1xpX2CMprDbIqdnpfXp9aNENT4xpgguwDBk7NFq6Eqms/edit?usp=sharing)

________________________________________

