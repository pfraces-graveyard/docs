# Coding Dojo

## Randori Kata

By some means the group decides on a Kata to work on, perhaps the
*Dojo Organizer* suggests one. No-one need have prepared anything much
before the meeting.

*   Some mechanism for regular switching of the driver and copilot is chosen
    (eg *Time Box*, *Ping Pong*, *Micro Pairing*, *N Tests*, *Shout Louder*)
*   Two people step up to the keyboard and begin solving the Kata in hand
    start from scratch
*   Use TDD and *Baby Steps*
*   Remember to switch the pair at the keyboard according to the mechanism
    chosen
*   Everyone present is expected to follow what is going on, and make
    helpful suggestions.
*   The pair at the keyboard should explain what they are doing so everyone
    can follow.
*   The audience should give advice/suggest refactorings primarily on a
    *Green Bar*. At other times the pair at the keyboard may ask not to be
    interrupted.

Reference: [Randori Kata][1]

## Baby Steps

The next step to take should always be **as small as possible**.

If we proceed in very small steps, chances are that we can keep the next
step trivial. *Baby Steps* combined with *Rhythm Of Test First* really
boosts productivity.

Reference: [Baby Steps][2]

## Rhythm Of Test First

*   Write UT for Particular *Baby Step*
*   Run it, it should fail
*   If it is not failing - review the test it might be wrong
*   Written test should generate an interfaces
*   Write an implementation until the test is green
*   Goto the next *Baby Step*

Reference: [Rhythm Of Test First][3]

## Ping Pong

A mechanism for switching the pair at the keyboard when doing a
*Randori Kata*

*   The driver writes the first test and then hands the keyboard to the
    copilot
*   The new driver makes the test pass and does necessary refactoring. They
    then write the next test and pass the keyboard back.
*   The original driver now implements code to make the test pass, and
    refactors.
*   A new pair steps up to the keyboard and the current pair sit down in
    the audience.

Reference: [Ping Pong][4]

## Kata Catalogue

List of Kata exercises that people have tried at their Dojo meetings, which
links to more detailed descriptions of each Kata.

Reference: [Kata Catalogue][5]

[1]: http://codingdojo.org/cgi-bin/index.pl?RandoriKata
[2]: http://codingdojo.org/cgi-bin/index.pl?BabySteps
[3]: http://codingdojo.org/cgi-bin/index.pl?RhythmOfTestFirst
[4]: http://codingdojo.org/cgi-bin/index.pl?PingPong
[5]: http://codingdojo.org/cgi-bin/index.pl?KataCatalogue
