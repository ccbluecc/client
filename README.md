function greeting(someone) {
  const msg = `hello, ${someone}`
  if (someone == null || someone == undefined) {
    const msg = `hello, guest`
    return msg
  }
  return msg
}
module.exports = greeting
