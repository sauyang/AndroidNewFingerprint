# AndroidNewFingerprint


Starting Initializing as below :


private void startBiometricAuthHelper() {
        biometricAuthHelper = new BiometricAuthHelper(this);
        if (!biometricAuthHelper.init()) {
            tvError.setText(biometricAuthHelper.getLastError());
        }
    }
    
    
    
For Fingerprint listener call back there are 3 as below:

 @Override
            public void onSuccess(String result) {
                if (isGetPass) {
                    tvError.setText("Success!!! Pass = " + result);
                } else {
                    tvError.setText("Encrypted pass = " + result);
                }
            }

            @Override
            public void onFailure(String message) {
                tvError.setText("Failed - " + message);
            }

            @Override
            public void onError(int errorCode, String errorString) {
                tvError.setText("Error needed - " + errorString);
            }
            
            
            
Call savePassword or getPassword for encryption and decrpytion. So that the password is encrypted and saved in storage.
