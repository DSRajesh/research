This code generates captchas of random sequence of 5 characters (digits and alphabets). Following steps have been followed to generate captcha:

1.	Generate a random  5 character sequence made of alphabets and digits (randomly selected 5 out of a 36 character vocabulary.
2.	Insert it into an 30x100 image area (with a particular background color and text size) created for this purpose. This forms a plain captcha 
3.	Deform this captcha image using scaling, shearing, rotation and translation using randomly generated  parameters. ( the skimage.transform library used for data augmentation in machine learning is used for this purpose) 
4.	Noise the deformed captcha image using Gaussian kernel with randomly generated sigma value
5.	Compute a transform which can modulate the deformed-noised image with a sinusoid of randomly decided frequency
6.	Display this final captcha image

Once the user enters the captcha characters it can be checked. If the user asks for an alternate captcha or for a new user similar randomly generated captchas can be generated like this


Note*     This line   rng = np.random.RandomState(40)   in the beginning of the program must be executed only one time i.e when the first captcha is generated. And during the later runs its execution must be disabled

