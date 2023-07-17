# Function to create a special "matrix" object that can cache its inverse
makeCacheMatrix <- function(x = matrix()) {
  inv <- NULL  # Initialize inverse matrix
  
  set <- function(y) {
    x <<- y  # Assign input matrix to 'x'
    inv <<- NULL  # Reset cached inverse
  }
  
  get <- function() {
    x  # Return the input matrix 'x'
  }
  
  getinverse <- function() {
    inv  # Return the cached inverse matrix
  }
  
  list(set = set, get = get, getinverse = getinverse)
}

# Function to compute the inverse of the special "matrix" object with caching
cacheSolve <- function(x) {
  inv <- x$getinverse()  # Try to retrieve the cached inverse
  
  if (!is.null(inv)) {
    message("Getting cached inverse...")
    return(inv)  # Return the cached inverse if available
  }
  
  data <- x$get()  # Retrieve the input matrix
  
  inv <- solve(data)  # Compute the inverse
  
  x$setinverse(inv)  # Cache the computed inverse
  
  inv  # Return the computed inverse
}
