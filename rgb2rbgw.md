## RGB to RGBW considering temperatur of white LED

Simple function in processing (java) to translate RGB values into RGBW 

'''
int[] rgb2rgbw(float r, float g, float b){
  

  
  // 6500: (255, 249, 253),
  float wR = 255.0;
  float wG = 249.0;
  float wB = 253.0;
  
  float wFRed = r * 255.0 / wR;
  float wFGreen = g * 255.0 / wG;
  float wFBlue = b * 255.0 / wB;
  
  float minWhite = min(wFRed, min(wFGreen, wFBlue));
  
  float oW = (minWhite <= 255 ? minWhite : 255);

  float oR = (r - minWhite * wR / 255);
  float oG = (g - minWhite * wG / 255);
  float oB = (b - minWhite * wB / 255);
  int[] ooVals = { int(oR), int(oG), int(oB), int(oW)}; 
  
  return ooVals;

}
'''
