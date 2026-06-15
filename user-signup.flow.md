# user roles
- superadmin
- support staff
- customer
- vendor

# user mgmt rules with backend endpoints
- superadmin only can register for superadmin and support staff role users, we call them portal users [future]
- vendors/customer can register themselves and activate themselves
- backend url for vendor registration: /api/vendor/register,
- login: /api/auth/login
  - in case of seller user or has seller role, isseller will be true,
  - in case of status active, isselleractive will be true
- backend url for customer reigstration: /api/customer/register, login: /api/auth/login
  - in case of customer user or has customer role, iscustomer will be true,
  - in case of status active, iscustomeractive will be true
- a single user can be both seller and customer
- super admin can enable or disable users, seller, customer
- super admin can register seller as customer also via `PUT /api/auth/super-admin/users/{userId}/buyer-role` and customer as seller also via `PUT /api/auth/super-admin/users/{userId}/seller-role`
- seller can also activate as customer also by self via `/api/auth/activate-buyer-role`
- customer can also activate as seller also by self via `/api/auth/activate-seller-role`

# fronend endpoints for user signup


# Seller Signup Flow
- Opens seller portal [adm-ecommerce.sebs.asia]
- signup
- email validation 
- -> if is is already registered as seller or buyer
- -> In case already registered as seller -> error message for duplicate email id, plz make login
- -> In case already registered as buyer -> error message for already registered as buyer, so login and activate seller feature from profile
- -> If not already registered, ask for email otp validation and complete the process

# Buyer Signup Flow
- Opens Customer portal [ecommerce.sebs.asia]
- signup
- email validation 
- -> if is is already registered as seller or buyer
- -> In case already registered as buyer -> error message for duplicate email id, plz make login
- -> In case already registered as seller -> error message for already registered as seller, so login and activate buyer feature from profile
- -> If not already registered, ask for email otp validation and complete the process

