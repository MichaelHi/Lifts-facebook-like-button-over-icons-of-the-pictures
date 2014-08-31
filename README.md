Lifts-facebook-like-button-over-icons-of-the-pictures
=====================================================

In my last repository I tried to fix the z-index of the facebook-like-box.
The fix works fine, but I found out, that the icons of the pictures still hide the facebook-like-flyout.
This can be fixed by a change of 2 z-indexes of the oxid.css.

/* ---Hier der Code --- */

.social span {
    float: left;
    z-index: 66;
}

.marker {
    position: absolute;
    width: 96px;
    height: 96px;
    border: 2px solid #eb6005;
    top: 0;
    left: 0;
    display: none;
    z-index: 33;
    
  /* --- Ende --- */
    
  Why did I not change .social span-z-index to 100 and leave .marker-z-index unchanged (99)?
  If .social span-z-index were 100, it would be too high for the cloudzoom--z-index, that is defined at cloudzoom.js (line 271) with 99. To keep cloudzoom-z-index unchanged (including the IE6 fix in this file), I recommend my solution.
