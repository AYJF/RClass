To make our life easier when reading from the training and test sets, we use a DataLoader rather
than creating one from scratch, as we did in Section 3.2. Recall that at each iteration, a DataLoader
reads a minibatch of data with size batch_size each time.
During training, reading data can be a significant performance bottleneck, especially when our
model is simple or when our computer is fast. A handy feature of Gluonʼs DataLoader is the ability
to use multiple processes to speed up data reading. For instance, we can set aside 4 processes to
read the data (via num_workers). Because this feature is not currently supported on Windows the
following code checks the platform to make sure that we do not saddle our Windows-using friends
with error messages later on.

Just as we implemented linear regression from scratch, we believe that multiclass logistic (soft-
max) regression is similarly fundamental and you ought to know the gory details of how to imple-
ment it yourself. As with linear regression, after doing things by hand we will breeze through an
implementation in Gluon for comparison. To begin, let us import the familiar packages.
