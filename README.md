Buffer Text Input Layout
-------------------------

This is a simple customisation of the TextInputLayout found in the Design Support Library.

Whilst this is an awesome component that we've made great use of, we wanted to be able to display
the counter so that the value displayed was:

- Descending
- Only visible when we reach a certain number of characters away from the maximum counter value

Hence why we created this simple component :)

##Ascending

![Ascending](/art/ascending.gif)

##Descending

![Descending](/art/descending.gif)

##Standard

![Standard](/art/standard.gif)


##Display when a given count away from the maximum value

![Hidden](/art/hidden.gif)


#How to use

In exactly the same way as the support library! Simply wrap an edit text field like so:

    <org.buffer.android.buffertextinputlayout.BufferTextInputLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            app:counterEnabled="true"
            app:counterMaxLength="10"
            app:counterOverflowTextAppearance="@style/counterOverride"
            app:counterTextAppearance="@style/counterText"
            app:hintEnabled="true"
            app:counterMode="ascending">

        <EditText
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="@string/text_hint" />

    </org.buffer.android.buffertextinputlayout.BufferTextInputLayout>


#Setting attributes via XML

In our XML layout, we can set two extra attributes for the BufferTextInputLayout:

- app:counterMode -> Set the mode in which the counter should use when being displayed (DESCENDING, ASCENDING, STANDARD)
- app:displayFromCount -> Set the value for which how many characters should be remaining until the counter becomes visible

e.g

    app:displayFromCount="5"
    app:counterMode="descending"


#Setting attributes programmatically

- setCounterMode(CounterMode counterMode) -> Set the mode in which the counter should use when being displayed (DESCENDING, ASCENDING, STANDARD)
- setCharactersRemainingUntilCounterDisplay(int remainingCharacters) -> Set the value for which how many characters should be remaining until the counter becomes visible

e.g.

    bufferTextInputLayout.setCounterMode(CounterMode.DESCENDING);
    bufferTextInputLayout.setCharactersRemainingUntilCounterDisplay(40);