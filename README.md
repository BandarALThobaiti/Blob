blobify manages binary memory blocks using a block, a range, and a cursor.
CThe blb_blob_set function writes data after verifying the cursor is within the allowed range.
The blb_blob_get function reads data from the current cursor position and stores it in a variable.
Both functions feature auto-incrementing, moving the cursor forward by the step size after a successful operation.
If you perform a set followed immediately by a get, the cursor moves to the next position and will not read the same byte.
Creating, deleting, and controlling the blob, its range, and its cursor are managed via dedicated functions in blobify.c
The library prevents out-of-bounds operations and halts modifications if the cursor or range is set to fixed. 
