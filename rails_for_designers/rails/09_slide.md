!SLIDE
# Rails Routing #

!SLIDE
# Resources #
    @@@Code
    # config/routes.rb
    resources :users

!SLIDE smaller
    @@@Code
    GET /users
    match "users" => "users#index"
    { :controller => "users" :action => "index" }
    users_path

!SLIDE smaller
    @@@Code
    GET /users/new
    match "users/new" => "users#new"
    { :controller => "users", :action => "new" }
    new_user_path

!SLIDE smaller
    @@@Code
    POST /users
    match "users" => "users#create"
    { :controller => "users", :action => "create" }
    users_path

!SLIDE smaller
    @@@Code
    GET /users/17
    match "users/:id" => "users#show"
    { :controller => "users", :action => "show" }
    user_path(:user)

!SLIDE smaller
    @@@Code
    GET /users/17/edit
    match "users/:id/edit" => "users#edit"
    { :controller => "users" :action => "edit" }
    edit_user_path(:user)

!SLIDE smaller
    @@@Code
    PUT /users/17
    match "users/:id" => "users#update"
    { :controller => "users", :action => "update" }
    user_path(:user)

!SLIDE smaller
    @@@Code
    DELETE /users/17
    match "users/:id" => "users#destroy"
    { :controller => "users", :action => "destroy" }
    user_path(:user)