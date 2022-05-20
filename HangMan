@words = ("computer","radio","calculator","teacher","bureau","police","geometry","president","subject","country","enviroment","classroom","animals","province","month","politics","puzzle","instrument","kitchen","language","vampire","ghost","solution","service","software","virus25","security","phonenumber","expert","website","agreement","support","compatibility","advanced","search","triathlon","immediately","encyclopedia","endurance","distance","nature","history","organization","international","championship","government","popularity","thousand","feature","wetsuit","fitness","legendary","variation","equal","approximately","segment","priority","physics","branche","science","mathematics","lightning","dispersion","accelerator","detector","terminology","design","operation","foundation","application","prediction","reference","measurement","concept","perspective","overview","position","airplane","symmetry","dimension","toxic","algebra","illustration","classic","verification","citation","unusual","resource","analysis","license","comedy","screenplay","production","release","emphasis","director","trademark","vehicle","aircraft","experiment");
$next =1;
while($next){
$next=0;
$word=$words[rand @words ];
$len = length $word;
@play=();
@guesses=();
$len1=0;
$tries=0;
for ($i=0; $i < $len; $i++) 
{
    $play[$i]="_";
}
$tries=0;
$wi=0;
while(!$wi)
{
    $chec=0;
    $inword=0;
    $guess;
    print "\n\nword : @play \n";
    print "guesses : @guesses\n";
    while(!$chec)
    {
        print "Enter your guess : ";
        $guess = <STDIN>;
        chomp($guess);
        $leng=length($guess);
        
        $chec=check1($guess,$len1,@guesses);
        if($chec==0){
        print "You already guessed $guess\n";}
        if($leng ne 1)
        {
            $chec=0;
            print "enter character not any other\n";
        }
    }
    $len1++;
    @array=$guess;
    @guesses=(@guesses,@array);
    &check2($inword,$guess,$len,$word,@play);
    
    if($inword==0)
    {
        print "Wrong guess - ";
        print 5-$tries;
        print " parts left\n";
        $tries=$tries+1;
        &fgd($tries);
    }
    else
    {
        print "Good guess - ";
        print 6-$tries;
        print " parts left\n";
        &fgd($tries);
        $wi=win(@play);
        if($wi==1)
        {
            print "win";
            print "Do you want play again 1-yes,0-no:";
            $new = <STDIN>;
            chomp($new);
            $next=$new;
            break;
        }
    }
    if($tries>=6)
    {
        print"you lost\n";
        print "$word is the word\n";
        print "Do you want play again 1-yes,0-no:";
        $new = <STDIN>;
        chomp($new);
        $next=$new;
        $wi=1;
    }
}}


sub check1{
    ($guess,$len1, @guesses) = @_;
    for ($i = 0; $i < $len1; $i++)
    {
        if($guesses[$i] eq $guess)
        {
            return 0;
        }
    }
    return 1;
}

sub check2{
    ($inword,$guess,$len,$word,@play)=@_;
    for ($i = 0; $i < $len; $i++)
    {
        $w= substr($word, $i, 1);
        if($w eq $guess)
        {
            $play[$i]=$guess;
            $inword=1;
        }
    }
}

sub win{
    (@play)=@_;
    for ($i = 0; $i < $len; $i++)
    {
        if($play[$i] eq "_")
        {
            return 0;
        }
    }
    return 1;
}

sub fgd{
    ($tries)=@_;
    print "     ________\n";
    print "     |      |\n";
    if($tries>=1){
    print "     |      O\n";}
    else{
    print "     |       \n";}
    if($tries==2){
    print "     |      |\n";}
    else {if($tries==3){
    print "     |     \\|\n";}
    else {if($tries>3){
    print "     |     \\|/\n";}
    else{
    print "     |       \n";}}}
    if($tries>=2){
    print "     |      | \n";}
    else{
    print "     |       \n";}
    if($tries==5){
    print "     |     /\n";}
    elsif($tries==6){
    print "     |     / \\ \n";}
    else{
    print "     |\n"}
    print "     |\n";
    print "     |\n";
    print "_____|______\n";
}
