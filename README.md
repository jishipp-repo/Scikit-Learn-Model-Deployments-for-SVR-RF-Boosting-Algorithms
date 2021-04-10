# Scikit-Learn Model Deployment for SVR, RF, Boosting Regression Algorithms
Scikit-Learn models can be efficiently stored in a encrypted format for the deployment purposes. This way dependency on un-protected pickle or joblib files can be eliminated. 

The current implentation uses AES (Advanced Encryption Standard) algorithmn (Crypto package) while saving the JSON file containing model parameters. AES uses symmetric key encryption, which involves the use of only one secret key to cipher and decipher information. *encrypt_json* function encrypts the models and store it locally. *decrypt_json* function loads the encrypted file and decrypts it. 

While saving the machine learning models (SVR, RF & Gradient Boosting provided here) from Sklearn package using the *save_model_json* function, it uses the finalized parameters obtained after training and cross-validation. The pre-processing (Standardization) values for the models also gets stored in the final model. Please note that for tree based models the whole trees of the algorithmn (in if-else functional form),  obtained through *tree_to_list* function, gets stored in the encrypted file.

Developed a *custom_predict_json* function to obtain the models prediction value based on the model type (SVR/RF/Gradient Boosting).
