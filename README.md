# Low distortion embedding of finite metric spaces

This repository contains an implementation of the Bourgain algorithm:
Given the n-point metric space (X,d), we map every point x in X to p(x), an O(log(n)^2)-dimensional vector. 
Coordinates in p(.) correspond to subset S of X, and the S-th coordinate in p(x) is simply d(x,S), the minimum of d(x,y) over all y in S.
To define the map p, we need to specify, then, the collection of substes S that we utilize. These sets are selected randomly.
Namely, you randomly select O(log(n)) sets of size 1, another O(log(n)) sets of size 2, of size 4, 8, ..., n/2.
The running time of the algorithm is approximately O(log(n)^2*n^2*t), provided the distances are computed at constant time t.

# What is it useful for?

Suppose you have in machine learning a dataframe, which has mixed categorical and numerical values, but your favourite machine learning algorithm works only with numeric features. The options you have is to one-hot-encode the categorical features, or you could directly embed every instance of the sample in euclidean space. This way you have only numerical features and can ran your algorithm. 

# Is there some guarantee, that this will work?

Well, the Bourgain Theorem guarantees, that every finite metric space X with n points will be embedded in euclidean space with distortion at most log(n). This is a good thing, since there is a theorem, which proves, that it doesn't go any better.

