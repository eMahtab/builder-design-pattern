# Builder Pattern


### User.java

```java
package builder;

public class User {
    private String firstName;
    private String lastName;
    private String email;
    private String gender;
    private String country;
    private String mobileNumber;
    private String pincode;
    
    private User(UserBuilder builder) {
    	this.firstName = builder.firstName;
    	this.lastName = builder.lastName;
    	this.email = builder.email;
    	this.gender = builder.gender;
    	this.country = builder.country;
    	this.mobileNumber = builder.country;
    	this.pincode = builder.pincode;
    }
    
    public static class UserBuilder {
    	private String firstName;
        private String lastName;
        private String email;
        private String gender;
        private String country;
        private String mobileNumber;
        private String pincode;
        
        public UserBuilder() {}
        
        public UserBuilder setFirstName(String firstName) {
        	this.firstName = firstName;
        	return this;
        }
        
        public UserBuilder setLastName(String lastName) {
        	this.lastName = lastName;
        	return this;
        }
        
        public UserBuilder setEmail(String email) {
        	this.email = email;
        	return this;
        }
        
        public UserBuilder setGender(String gender) {
        	this.gender = gender;
        	return this;
        }
        
        public UserBuilder setCountry(String country) {
        	this.country = country;
        	return this;
        }
        
        public UserBuilder setMobileNumber(String mobileNumber) {
        	this.mobileNumber = mobileNumber;
        	return this;
        }
        
        public UserBuilder setPincode(String pincode) {
        	this.pincode = pincode;
        	return this;
        }
        
        public User build() {
        	return new User(this);
        }
    }

}

```

### App.java
```java
import builder.User.UserBuilder;

public class App {
	public static void main(String[] args) {
		UserBuilder userBuilder =  new User.UserBuilder();
		User user = userBuilder.setFirstName("Mahtab")
				   .setLastName("Alam")
				   .setEmail("test@gmail.com")
				   .setCountry("India")
				   .setMobileNumber("9999999999")
				   .setGender("Male")
				   .setPincode("309832")
				   .build();
		
		System.out.println(user);			
	}
}
```
