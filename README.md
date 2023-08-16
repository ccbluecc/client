<p>function greeting(someone) {
<p>  const msg = `hello, ${someone}`
<p>  if (someone == null || someone == undefined) {
<p>    const msg = `hello, guest`
<p>    return msg
<p>  }
<p>  return msg
<p>}
<p>module.exports = greeting
