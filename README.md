assignment_week3_Wenjun_Peng
============================
 	## the following pair of functions create a special object that stores a metrix and caches its inversion

 	## the first function, makeCacheMatrix is used to create a special "matrix", 
 	## a list to set and get the value of the matrix and solve and store the inversion

 	makeCacheMatrix <- function(x = matrix()) {
 
 	s <- NULL
 	set <- function(y){
 	x <<-y
 	s <<-NULL
 	}
 	get <- function() x
 	solve<-solve(x)
	setsolve <- function(solve) s<<-solve
 	getsolve <- function() s
 	list(set=set,get=get,setsolve=setsolve,getsolve=getsolve)
 	}

 	##the second function returns the stored invertion or solves the inversion of the matrix not stored
 
 	cacheSolve <- function(x, ...){
 	s <- x$getsolve()
 	if(!is.null(s)){
 	message("getting cached data")
 	return (s)
 	}
 	data <- x$get()
 	s <-solve (data,...)
 	x$setsolve(s)
 	s

	}
